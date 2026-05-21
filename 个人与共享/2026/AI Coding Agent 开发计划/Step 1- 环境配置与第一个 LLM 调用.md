## 1. 创建项目目录

打开终端，运行以下命令：

```bash
# 创建项目目录
mkdir ai-coding-agent
cd ai-coding-agent

# 创建 Python 虚拟环境
python -m venv venv

# 激活虚拟环境
# macOS/Linux:
source venv/bin/activate
# Windows:
# .\venv\Scripts\activate

# 创建基础目录结构
mkdir -p src/agent src/tools src/llm src/memory tests
touch src/__init__.py src/agent/__init__.py src/tools/__init__.py src/llm/__init__.py src/memory/__init__.py
```

---

## 2. 安装依赖

创建 `requirements.txt` 文件：

```
openai>=1.0.0
python-dotenv>=1.0.0
rich>=13.0.0
typer>=0.9.0
```

安装依赖：

```bash
pip install -r requirements.txt
```

---

## 3. 配置 API Key

创建 `.env` 文件（**记得加入 .gitignore**）：

```
OPENAI_API_KEY=sk-your-api-key-here
```

> [!important]
> 
> **安全提醒**：永远不要将 API Key 提交到 Git 仓库！

---

## 4. 第一个 LLM 调用 🎉

创建 `src/llm/``[client.py](http://client.py)`：

```python
import os
from openai import OpenAI
from dotenv import load_dotenv

# 加载环境变量
load_dotenv()

class LLMClient:
    """LLM 客户端封装"""
    
    def __init__(self, model: str = "gpt-4o"):
        self.client = OpenAI(api_key=os.getenv("OPENAI_API_KEY"))
        self.model = model
        self.system_prompt = """你是一个专业的编程助手。
你可以帮助用户编写、解释和调试代码。
请用简洁清晰的方式回答问题。"""
    
    def chat(self, message: str) -> str:
        """发送消息并获取回复"""
        response = self.client.chat.completions.create(
            model=self.model,
            messages=[
                {"role": "system", "content": self.system_prompt},
                {"role": "user", "content": message}
            ],
            temperature=0.7,
        )
        return response.choices[0].message.content


# 快速测试
if __name__ == "__main__":
    llm = LLMClient()
    
    # 测试一个简单的编程问题
    question = "用 Python 写一个计算斐波那契数列的函数"
    print(f"问题: {question}\n")
    
    answer = llm.chat(question)
    print(f"回答:\n{answer}")
```

---

## 5. 运行测试

```bash
python src/llm/client.py
```

如果一切正常，你会看到 AI 生成的斐波那契函数代码！

> [!important]
> 
> **恭喜！** 你已经完成了第一步——成功调用 LLM 并获得回复。

---

## 6. 进阶：添加多轮对话支持

更新 `src/llm/``[client.py](http://client.py)`，添加对话历史：

```python
from typing import List, Dict

class LLMClient:
    """支持多轮对话的 LLM 客户端"""
    
    def __init__(self, model: str = "gpt-4o"):
        self.client = OpenAI(api_key=os.getenv("OPENAI_API_KEY"))
        self.model = model
        self.system_prompt = """你是一个专业的编程助手。
你可以帮助用户编写、解释和调试代码。
请用简洁清晰的方式回答问题。"""
        # 对话历史
        self.messages: List[Dict[str, str]] = [
            {"role": "system", "content": self.system_prompt}
        ]
    
    def chat(self, message: str) -> str:
        """发送消息并获取回复（保持对话历史）"""
        # 添加用户消息
        self.messages.append({"role": "user", "content": message})
        
        # 调用 API
        response = self.client.chat.completions.create(
            model=self.model,
            messages=self.messages,
            temperature=0.7,
        )
        
        # 获取回复
        assistant_message = response.choices[0].message.content
        
        # 保存到历史
        self.messages.append({"role": "assistant", "content": assistant_message})
        
        return assistant_message
    
    def clear_history(self):
        """清空对话历史"""
        self.messages = [
            {"role": "system", "content": self.system_prompt}
        ]
```

---

## 下一步

> [!important]
> 
> 完成后，进入 **Step 2: 构建基础 CLI 界面**，让我们的 Agent 可以在终端中交互使用。