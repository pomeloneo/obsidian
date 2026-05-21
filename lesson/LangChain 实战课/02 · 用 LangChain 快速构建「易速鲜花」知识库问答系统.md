> [!important]
> 
> **原文链接**：[极客时间专栏](https://time.geekbang.org/column/article/699436)

[![](https://static001.geekbang.org/resource/image/03/82/03bb1346abb0dae7119f5yy216ab3582.jpg)](https://static001.geekbang.org/resource/image/03/82/03bb1346abb0dae7119f5yy216ab3582.jpg)

课程封面

你好，我是黄佳，欢迎来到 LangChain 实战课！

在深入讲解 LangChain 的每一个具体组件之前，我想带着你从头完成一个很实用、很有意义的实战项目。目的就是让你直观感受一下 LangChain 作为一个基于大语言模型的应用开发框架，功能到底有多么强大。

---

## 项目及实现框架

### 项目概述

**核心痛点**：

- 信息分散于内部网和 HR 部门目录各处，不便查询

- 文档过于冗长，员工无法第一时间找到想要的内容

- 公司政策已更新，但员工手头的文档还是旧版内容

**解决方案**：开发一套基于内部知识手册的 **Doc-QA** 系统。这个系统将充分利用 LangChain 框架，处理员工手册相关问题，理解员工问题并给出精准答案。

---

### 开发框架

下图描述了通过 LangChain 框架实现知识库文档系统的整体框架：

[![](https://static001.geekbang.org/resource/image/c6/bf/c66995f1bf8575fb8fyye6293200eabf.jpg?wh=1393x697)](https://static001.geekbang.org/resource/image/c6/bf/c66995f1bf8575fb8fyye6293200eabf.jpg?wh=1393x697)

基于数据源的文档问答系统开发框架

整个框架分为 **三个部分**：

> 本示例聚焦于**非结构化数据**的处理。

---

### 核心实现机制

项目的核心是下图所示的**数据处理管道（Pipeline）**：

[![](https://static001.geekbang.org/resource/image/73/87/73a46eecd42038961db9067e75de3387.jpg?wh=2509x799)](https://static001.geekbang.org/resource/image/73/87/73a46eecd42038961db9067e75de3387.jpg?wh=2509x799)

文档问答系统的数据处理管道

> [!important]
> 
> **具体流程分为 5 步**：
> 
> 1. **Loading**：文档加载器把 Documents 加载为 LangChain 能够读取的形式
> 
> 1. **Splitting**：文本分割器把 Documents 切分为指定大小的"文档块"
> 
> 1. **Storage**：将分割好的"文档块"以"嵌入"(Embedding) 形式存储到向量数据库
> 
> 1. **Retrieval**：从存储中检索分割后的文档（如通过余弦相似度找到相似嵌入片）
> 
> 1. **Output**：把问题和相似嵌入片传递给 LLM，生成答案

---

## 数据的准备和载入

"易速鲜花"的内部资料包括 pdf、word 和 txt 格式的各种文件：

[![](https://static001.geekbang.org/resource/image/b6/ff/b69956a706112266df404eee953459ff.jpg?wh=402x224)](https://static001.geekbang.org/resource/image/b6/ff/b69956a706112266df404eee953459ff.jpg?wh=402x224)

文件目录结构

其中一个文档示例：

[![](https://static001.geekbang.org/resource/image/93/24/931a55af4f0a3842a640d95c2c4bf224.jpg?wh=1630x1073)](https://static001.geekbang.org/resource/image/93/24/931a55af4f0a3842a640d95c2c4bf224.jpg?wh=1630x1073)

文档内容示例

使用 LangChain 中的 `document_loaders` 加载各种格式的文本文件：

```python
import os
os.environ["OPENAI_API_KEY"] = '你的Open AI API Key'

from langchain.document_loaders import PyPDFLoader
from langchain.document_loaders import Docx2txtLoader
from langchain.document_loaders import TextLoader

# 设置文件目录
base_dir = '.\\OneFlower'
documents = []

# 遍历加载不同格式的文件
for file in os.listdir(base_dir):
    file_path = os.path.join(base_dir, file)
    if file.endswith('.pdf'):
        loader = PyPDFLoader(file_path)
        documents.extend(loader.load())
    elif file.endswith('.docx'):
        loader = Docx2txtLoader(file_path)
        documents.extend(loader.load())
    elif file.endswith('.txt'):
        loader = TextLoader(file_path)
        documents.extend(loader.load())
```

> [!important]
> 
> **为什么需要 OpenAI API Key？**
> 
> - 用 OpenAI 的 **Embedding 模型**为文档做嵌入
> 
> - 调用 OpenAI 的 **GPT 模型**来生成问答系统中的回答
> 
> 当然，LangChain 支持的大模型不仅限于 OpenAI，你完全可以替换为其他开源模型。

> [!important]
> 
> **注意**：运行代码时可能需要安装 `PyPDF`、`Docx2txt` 等库，通过 `pip install` 安装即可。

---

## 文本的分割

将加载的文本分割成更小的块，以便进行嵌入和向量存储。使用 `RecursiveCharacterTextSplitter`：

```python
from langchain.text_splitter import RecursiveCharacterTextSplitter

text_splitter = RecursiveCharacterTextSplitter(chunk_size=200, chunk_overlap=10)
chunked_documents = text_splitter.split_documents(documents)
```

> 文档被切成了约 **200 字符**的文档块，为存储进向量数据库做准备。

---

## 向量数据库存储

将分割后的文本转换为嵌入形式，并存储在向量数据库中。

### 什么是词嵌入？

> [!important]
> 
> **词嵌入 (Word Embedding)** 是将文字或词语转换为一系列数字（向量）的技术。这些数字捕获了词的含义和上下文，语义相似的词在数字空间中会比较接近。

**示例**：

从向量可以看出，"国王"和"皇帝"的向量相似，而与"苹果"相差很大——因为语义不同。

### 什么是向量数据库？

> [!important]
> 
> **向量数据库**是专门用于存储和搜索向量形式数据的数据库。它具备高效存储和处理高维向量数据的能力，更好地支持涉及非结构化数据处理的 AI 应用。

[![](https://static001.geekbang.org/resource/image/e3/16/e3c7e244b15f9527a4eb811e550a8f16.png?wh=2989x1805)](https://static001.geekbang.org/resource/image/e3/16/e3c7e244b15f9527a4eb811e550a8f16.png?wh=2989x1805)

向量数据库可以存储各种非结构化的数据（图片来源网络）

常见向量数据库：**Pinecone**、**Chroma**、**Qdrant** 等。

### 实现代码

使用开源向量数据库 **Qdrant**：

```python
from langchain.vectorstores import Qdrant
from langchain.embeddings import OpenAIEmbeddings

vectorstore = Qdrant.from_documents(
    documents=chunked_documents,
    embedding=OpenAIEmbeddings(),
    location=":memory:",
    collection_name="my_documents",
)
```

> [!important]
> 
> 需要安装：`pip install qdrant-client`

> 至此，易速鲜花的所有内部文档都以"文档块嵌入片"格式存储在向量数据库中了。

---

## 相关信息的获取

文档存储到向量数据库后，需要根据问题提取最相关的信息。基本方式是**把问题也转换为向量**，然后与数据库中的向量进行比较。

### 向量比较方法

[![](https://static001.geekbang.org/resource/image/32/7a/32db77431433da86d9f818037752bd7a.png?wh=1600x1320)](https://static001.geekbang.org/resource/image/32/7a/32db77431433da86d9f818037752bd7a.png?wh=1600x1320)

语义相似的向量之间距离近或方向相似（图片来源网络）

> [!important]
> 
> **本项目选择**：余弦相似度
> 
> 因为我们正在处理文本数据，目标是从语义上理解和比较问题与答案。

### 实现代码

创建 **RetrievalQA 链**（检索式问答模型）：

```python
import logging
from langchain.chat_models import ChatOpenAI
from langchain.retrievers.multi_query import MultiQueryRetriever
from langchain.chains import RetrievalQA

# 配置日志
logging.basicConfig()
logging.getLogger('langchain.retrievers.multi_query').setLevel(logging.INFO)

# 创建聊天模型
llm = ChatOpenAI(model_name="gpt-3.5-turbo", temperature=0)

# 创建检索器
retriever_from_llm = MultiQueryRetriever.from_llm(
    retriever=vectorstore.as_retriever(), 
    llm=llm
)

# 创建问答链
qa_chain = RetrievalQA.from_chain_type(llm, retriever=retriever_from_llm)
```

**RetrievalQA 链的两大核心组成**：

> 本地文档检索的知识很重要，因为从互联网训练的大模型不可能拥有"易速鲜花"作为私营企业的内部知识。

---

## 生成回答并展示

这一步是问答系统的主要 **UI 交互**部分，使用 Flask 构建 Web 应用。

### Flask 应用代码

```python
from flask import Flask, request, render_template

app = Flask(__name__)

@app.route('/', methods=['GET', 'POST'])
def home():
    if request.method == 'POST':
        question = request.form.get('question')
        result = qa_chain({"query": question})
        return render_template('index.html', result=result)
    return render_template('index.html')

if __name__ == "__main__":
    app.run(host='0.0.0.0', debug=True, port=5000)
```

### HTML 模板关键代码

```html
<body>
    <div class="container">
        <div class="header">
            <h1>易速鲜花内部问答系统</h1>
            <img src=" url_for('static', filename='flower.png') " alt="flower logo" width="200">
        </div>
        <form method="POST">
            <label for="question">Enter your question:</label><br>
            <input type="text" id="question" name="question"><br>
            <input type="submit" value="Submit">
        </form>
        {% if result is defined %}
            <h2>Answer</h2>
            <p> result.result </p>
        {% endif %}
    </div>
</body>
```

### 项目目录结构

[![](https://static001.geekbang.org/resource/image/21/3e/2110cd73ddb8677f9b188d41c589c73e.png?wh=710x465)](https://static001.geekbang.org/resource/image/21/3e/2110cd73ddb8677f9b188d41c589c73e.png?wh=710x465)

项目目录结构

### 运行效果

运行程序后，访问 `[http://127.0.0.1:5000/](http://127.0.0.1:5000/)`：

[![](https://static001.geekbang.org/resource/image/46/17/46b5b08c5f022f2c4c5975436b3e2d17.png?wh=567x338)](https://static001.geekbang.org/resource/image/46/17/46b5b08c5f022f2c4c5975436b3e2d17.png?wh=567x338)

问答系统成功检索到内部资料并作出回答

---

## 总结时刻

[![](https://static001.geekbang.org/resource/image/24/af/249c631211275e40f3e72d05dda976af.jpg?wh=2523x1058)](https://static001.geekbang.org/resource/image/24/af/249c631211275e40f3e72d05dda976af.jpg?wh=2523x1058)

整体流程回顾

> [!important]
> 
> **核心流程回顾**：
> 
> 1. 把本地知识切片后做 Embedding
> 
> 1. 存储到向量数据库中
> 
> 1. 把用户输入和检索到的本地知识传递给大模型
> 
> 1. 最终生成所需答案

**LangChain + LLM** 的配置就是使原本复杂的东西变得特别简单、易于操作。而这个任务在大模型和 LangChain 出现之前，实现起来可不是这么简单的。

### 详细脑图

[![](https://static001.geekbang.org/resource/image/78/c2/78a4b0435639b4db8c4e024d830a2ac2.jpg?wh=2482x1434)](https://static001.geekbang.org/resource/image/78/c2/78a4b0435639b4db8c4e024d830a2ac2.jpg?wh=2482x1434)

知识点脑图

---

## 思考题

1. 请用自己的话简述这个基于文档的 QA（问答）系统的实现流程？

1. LangChain 支持很多种向量数据库，你能否用另一种常用的向量数据库 **Chroma** 来实现这个任务？

1. LangChain 支持很多种大语言模型，你能否用 HuggingFace 网站提供的开源模型 **google/flan-t5-x1** 代替 GPT-3.5 完成这个任务？

> 题目较多，可以选择性尝试，期待在留言区看到你的分享！

---

## 延伸阅读

- [LangChain 官方文档对 Document QA 系统设计及实现的详细说明](https://python.langchain.com/docs/use_cases/question_answering/)

- [HuggingFace 官网上的文档问答资源](https://huggingface.co/tasks/document-question-answering)

- 论文：_Open Question Answering over Tables and Text_ (Chen et al., ICLR 2021)