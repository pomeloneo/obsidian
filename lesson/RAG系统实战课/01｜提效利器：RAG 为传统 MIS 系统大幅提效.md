> [!important]
>
> 原文链接：[极客时间](https://time.geekbang.org/column/article/806091)

[![](https://static001.geekbang.org/resource/image/8a/53/8a748c4ac2dcbf64753dcda8353f2a53.jpg)](https://static001.geekbang.org/resource/image/8a/53/8a748c4ac2dcbf64753dcda8353f2a53.jpg)

课程封面

你好，我是叶伟民。

开篇词里面我们提过，RAG 是传统软件开发人员加入 AI 浪潮的最快之路，但是这条路里面又分三条小路。

- **第一条**：直接跳槽换一份 RAG 工作（比如做大模型应用开发），成功率最小。

- **第二条**：在现有公司/团队里面开一个全新的 RAG 项目，成功率高一点但仍有难度，下一章再探讨。

- **第三条**：使用 RAG 改造自己所处的项目，成功率最高、难度最小。

因此我们安排在最前面讲解，也就是第一章要学习的实战案例——**传统 MIS 系统的 RAG 改造**。

今天这一讲，我们就先睹为快，看看传统 MIS 系统使用 RAG 改造前后的模样，同时搞定一些环境准备工作，方便我们把 MIS 系统乃至整个课程的配套代码运行起来。

---

## 用 RAG 改造传统 MIS 系统的收益

我们如果单纯出于自己想加入 AI 浪潮的私心，就想推进一个 RAG 改造项目，这样是很难获得上级或者客户等利益相关者同意的。我们必须要让他们看到改造系统所带来的收益，才可能让他们同意我们改造。

> [!important]
>
> **核心收益**：使用 RAG 改造传统 MIS 系统，最直观的收益就是可以**大幅减少用户的操作步骤和操作时间**，提高用户的工作效率。

---

## 项目改造入手点

如何入手改造项目，才能减少用户的操作步骤和操作时间，提高用户的工作效率呢？我们先从日常最熟悉的查询操作说起。

### 查询数据

原来的 MIS 系统想查询一条数据要经过以下步骤：

1. 找到数据查询界面入口（1 个步骤）

1. 打开数据查询界面（1 个步骤）

1. 输入 N 种查询条件（N 个步骤）

1. 点击"查询"按钮

> 总计 **2+N+1** 个步骤。如果用户可以使用自然语言查询，理想状态下只需要 **1 个步骤**，总计可以减少 **N+2** 个步骤。N 越多，节省越多。

另外如果可以结合准确率高的语音输入法，那么用户节省的时间更多。既然查询部分改成了自然语言，那么录入数据部分也可以相应地改为自然语言录入。

### 录入数据

传统 MIS 系统里，录入一条数据要经过以下步骤：

1. 找到数据管理界面入口（1 个步骤）

1. 打开数据管理界面（1 个步骤）

1. 点击"新建"按钮（1 个步骤）

1. 录入数据，操作 N 个输入控件（N 个步骤）

1. 点击"保存"按钮

> 总计 **3+N+1** 个步骤。如果用户可以使用自然语言录入数据，理想状态下只需要 **1 个步骤**，总计可以减少 **N+3** 个步骤。

### 语音输入

结合准确率高的语音输入法，能为用户节省的时间就会更多。既然录入部分改成了自然语言，那么修改数据和删除数据部分也可以相应地改为自然语言。

> [!important]
>
> 语音输入法属于操作系统配置部分，不属于软件应用开发部分，这里提到这个，更多是为了启发你的思路。

接下来，我们看看这个实战案例所要改造的 MIS 系统。

---

## 传统的 MIS 系统

这里我们使用一个 ERP 系统来代表传统的 MIS 系统。以其中一个子模块："销售管理"下面的"销售对账"为例。

### 录入数据流程

我们先看看录入数据部分，直观感受一下录入的操作流程。

**第一步**：点开左边的"销售管理"菜单。

[![](https://static001.geekbang.org/resource/image/f8/2b/f8d1baf82178bff10de6b06cf46ee02b.jpg?wh=2010x514)](https://static001.geekbang.org/resource/image/f8/2b/f8d1baf82178bff10de6b06cf46ee02b.jpg?wh=2010x514)

点开"销售管理"菜单

**第二步**：点击"销售对账"子菜单。

[![](https://static001.geekbang.org/resource/image/24/80/24129a307c80206f59f63ee9e9724180.jpg?wh=2010x495)](https://static001.geekbang.org/resource/image/24/80/24129a307c80206f59f63ee9e9724180.jpg?wh=2010x495)

点击"销售对账"子菜单

**第三步**：点击页面左上角的"添加"按钮。

[![](https://static001.geekbang.org/resource/image/80/a6/80639cd7ff8907820ab33d5139c83da6.jpg?wh=2010x499)](https://static001.geekbang.org/resource/image/80/a6/80639cd7ff8907820ab33d5139c83da6.jpg?wh=2010x499)

点击"添加"按钮

**第四步**：进入"添加数据"页面，操作 N 个输入控件。

[![](https://static001.geekbang.org/resource/image/5b/14/5b4f55a594ac9e6be3f77569c77aef14.jpg?wh=2010x505)](https://static001.geekbang.org/resource/image/5b/14/5b4f55a594ac9e6be3f77569c77aef14.jpg?wh=2010x505)

添加数据页面

**第五步**：点击"提交"按钮。

[![](https://static001.geekbang.org/resource/image/27/56/27b593a92c3bc050083bcb19a98c3756.jpg?wh=2010x507)](https://static001.geekbang.org/resource/image/27/56/27b593a92c3bc050083bcb19a98c3756.jpg?wh=2010x507)

点击"提交"按钮

经过 **3+N+1** 个步骤之后，我们终于录入完一条数据。

### RAG 改造后的录入

使用 RAG 改造之后，理想状态下只需要 **两个步骤**：

1. 输入你的问题

1. 点击"提交"按钮

系统会解析你输入的内容，将其转化为数据录入系统。

[![](https://static001.geekbang.org/resource/image/7f/b3/7fe48c8ea61a26081eca12a73025bab3.jpg?wh=2010x509)](https://static001.geekbang.org/resource/image/7f/b3/7fe48c8ea61a26081eca12a73025bab3.jpg?wh=2010x509)

RAG 改造后的界面——自然语言录入

---

### 查询数据流程

再来看看查询数据的操作。

**第一步**：点开左边的"销售管理"菜单。

[![](https://static001.geekbang.org/resource/image/0a/37/0aeec869d9e5f039yy53c23f5007c037.jpg?wh=2010x514)](https://static001.geekbang.org/resource/image/0a/37/0aeec869d9e5f039yy53c23f5007c037.jpg?wh=2010x514)

点开"销售管理"菜单

**第二步**：点击"销售对账"子菜单。

[![](https://static001.geekbang.org/resource/image/04/0b/045b8a965c40ef9413698381e88ed30b.jpg?wh=2010x1118)](https://static001.geekbang.org/resource/image/04/0b/045b8a965c40ef9413698381e88ed30b.jpg?wh=2010x1118)

点击"销售对账"子菜单

**第三步**：在 N 个输入控件输入查询条件，点击"搜索"按钮。

[![](https://static001.geekbang.org/resource/image/92/e0/920c066yy10c5a8f59a68c1d38c907e0.jpg?wh=2010x499)](https://static001.geekbang.org/resource/image/92/e0/920c066yy10c5a8f59a68c1d38c907e0.jpg?wh=2010x499)

输入查询条件

系统返回查询结果：

[![](https://static001.geekbang.org/resource/image/1d/d1/1defecbce2ddf278bd72482fe3cb25d1.jpg?wh=2010x498)](https://static001.geekbang.org/resource/image/1d/d1/1defecbce2ddf278bd72482fe3cb25d1.jpg?wh=2010x498)

查询结果展示

经过 **2+N+1** 个步骤之后，我们终于查询出数据了。

### RAG 改造后的查询

使用 RAG 改造之后，理想状态下只需要 **两个步骤**：

1. 输入你的问题

1. 点击"提交"按钮

系统会解析你输入的内容，将其转化为具体的查询条件来查询出数据。

[![](https://static001.geekbang.org/resource/image/7f/b3/7fe48c8ea61a26081eca12a73025bab3.jpg?wh=2010x509)](https://static001.geekbang.org/resource/image/7f/b3/7fe48c8ea61a26081eca12a73025bab3.jpg?wh=2010x509)

RAG 改造后的界面——自然语言查询

---

通过改造前后的比较，我们明显看出通过 RAG 改造传统 MIS 系统可以提升用户的工作效率。我们可以通过这点，说服用户等利益相关者同意使用 RAG 改造传统 MIS 系统。

> [!important]
>
> 即使使用 RAG 改造了传统 MIS 系统，我们也依旧**保留了传统 MIS 系统的界面**。使用 RAG 将系统改造到可以替换的程度，并非短期可以完成的工作。即使完成了，根据经验，还是会有部分用户坚持使用传统界面，所以我们还需要保留传统界面，这样遇到 RAG 不能很好工作的时候，用户还能够通过传统界面完成任务。

---

## 安装先决软件和配置环境

我们约定使用 **Windows 11** 操作系统，为了把这个 MIS 系统运行起来，需要先安装以下软件：

- **Python 3.9**

- **Miniconda**（或 Anaconda）

Python 相信各位同学都不陌生。这里我们着重了解一下 Miniconda 或 Anaconda，因为整个课程里都将使用它们。

### 为什么要使用 Miniconda 或 Anaconda

Miniconda 或 Anaconda 是两种常用的 Python 发行版，我们整个课程将使用它们来创建 Python 的虚拟环境。

任何软件开发项目都会遇到依赖冲突、全局环境混乱、升级难题等问题。Java 使用 Maven，.NET 使用 NuGet，Python 则使用**虚拟环境**。

---

## 虚拟环境概述

虚拟环境是一种用于创建隔离的 Python 环境的方法。每个虚拟环境都有自己的 Python 解释器和一套独立的 Python 库。使用虚拟环境可以带来以下好处：

- **依赖管理**：为不同的项目安装不同的库和版本，而不会相互冲突

- **版本控制**：为每个虚拟环境指定 Python 版本，不受全局环境更新影响

- **避免全局污染**：每个环境都是独立的，避免全局包过多导致的依赖问题和版本冲突

- **开发和生产一致性**：本地开发环境与生产环境使用相同的依赖和配置

- **安全性**：限制对全局系统的更改，提高安全性

- **灵活性**：为不同项目创建多个虚拟环境，按需定制

常用的虚拟环境工具：

|工具|说明|
|---|---|
|`venv`|Python 标准库自带，从 Python 3.3 开始提供|
|`virtualenv`|第三方工具，支持 Python 2.x|
|`Conda`|Anaconda 的一部分，提供包管理和跨语言支持|

使用虚拟环境是 Python 开发中的最佳实践之一，可以帮助开发者管理项目依赖，确保项目的可移植性和可重复性。

---

## 初识 Conda

Conda 有两个版本：

|版本|特点|适用场景|
|---|---|---|
|**Anaconda**（完整版）|预装 conda、Python、众多科学计算包和工具|需要开箱即用的完整环境|
|**Miniconda**（精简版）|只包含 Conda 包管理器和 Python 解释器，体积小、启动快|只需要 Conda 包管理功能，按需安装|

---

## 安装 Miniconda

> [!important]
>
> 如果你之前安装过 Anaconda，直接使用即可，跳过此步骤。

**第一步**：使用浏览器打开 [清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/)，搜索 `anaconda`，点击搜索到的链接。

[![](https://static001.geekbang.org/resource/image/9b/48/9beb49c80606caf7a8142bac9d897748.jpg?wh=1990x321)](https://static001.geekbang.org/resource/image/9b/48/9beb49c80606caf7a8142bac9d897748.jpg?wh=1990x321)

搜索 anaconda

**第二步**：点击 `miniconda`。

[![](https://static001.geekbang.org/resource/image/64/3d/648e885d02246540ebb0a24e4755673d.jpg?wh=1940x521)](https://static001.geekbang.org/resource/image/64/3d/648e885d02246540ebb0a24e4755673d.jpg?wh=1940x521)

点击 miniconda 目录

**第三步**：点击 `Miniconda3-py39_23.5.2-0-Windows-x86_64.exe` 下载。

[![](https://static001.geekbang.org/resource/image/76/79/7603d89cb790db2e6811b819f9540e79.jpg?wh=1930x330)](https://static001.geekbang.org/resource/image/76/79/7603d89cb790db2e6811b819f9540e79.jpg?wh=1930x330)

下载安装包

下载之后，一路按默认安装即可。

### 确认安装成功

点击开始菜单，输入 `conda`，应该弹出以下界面：

[![](https://static001.geekbang.org/resource/image/6d/1e/6db8b680d00f5943ea6c1f2c979b681e.jpg?wh=1916x412)](https://static001.geekbang.org/resource/image/6d/1e/6db8b680d00f5943ea6c1f2c979b681e.jpg?wh=1916x412)

开始菜单搜索 conda

点击 **Anaconda Powershell Prompt**，弹出命令行界面：

[![](https://static001.geekbang.org/resource/image/2b/0c/2ba0c6930f02199488638bd9bc99d30c.jpg?wh=1939x137)](https://static001.geekbang.org/resource/image/2b/0c/2ba0c6930f02199488638bd9bc99d30c.jpg?wh=1939x137)

Anaconda Powershell Prompt

输入以下命令验证安装：

```bash
conda --version
```

[![](https://static001.geekbang.org/resource/image/4d/38/4df4b7098040126f0558eaa63934yy38.jpg?wh=1942x200)](https://static001.geekbang.org/resource/image/4d/38/4df4b7098040126f0558eaa63934yy38.jpg?wh=1942x200)

验证 conda 版本

---

## 虚拟环境搭建 & 系统运行

安装完 Miniconda 之后，我们还要搭建虚拟环境，并把 MIS 系统运行起来。

### 创建虚拟环境

继续使用 Anaconda Powershell Prompt，输入以下命令：

```bash
conda create -n rag1 python=3.9
```

> 这里的 `rag1` 是虚拟环境的名称。

[![](https://static001.geekbang.org/resource/image/e0/35/e0a39b7b7151c5763b3d95902212d835.jpg?wh=1944x336)](https://static001.geekbang.org/resource/image/e0/35/e0a39b7b7151c5763b3d95902212d835.jpg?wh=1944x336)

创建虚拟环境

当弹出提示时，输入 `y` 确认：

[![](https://static001.geekbang.org/resource/image/ec/y2/ec475a488984e50886a307f56c566yy2.jpg?wh=1931x193)](https://static001.geekbang.org/resource/image/ec/y2/ec475a488984e50886a307f56c566yy2.jpg?wh=1931x193)

确认安装

如果一切顺利，将会出现以下界面：

[![](https://static001.geekbang.org/resource/image/95/c1/95ffde79585bdbda6ee35c489a1cafc1.jpg?wh=1944x1041)](https://static001.geekbang.org/resource/image/95/c1/95ffde79585bdbda6ee35c489a1cafc1.jpg?wh=1944x1041)

虚拟环境创建成功

### 激活虚拟环境

环境创建好以后，输入以下命令激活：

```bash
conda activate rag1
```

如果一切顺利，命令行开头的 `base` 将会变成 `rag1`：

[![](https://static001.geekbang.org/resource/image/70/88/70faf77fd5bc2yy7d19ca83b99b84f88.jpg?wh=1941x181)](https://static001.geekbang.org/resource/image/70/88/70faf77fd5bc2yy7d19ca83b99b84f88.jpg?wh=1941x181)

激活虚拟环境

### 下载源代码

激活了虚拟环境之后，下载这一章的配套源代码。

### 安装依赖

下载和解压完源代码之后，回到 Anaconda Powershell Prompt，进入源代码目录：

```bash
cd 源代码解压后的目录
cd 实战案例1\改造前
```

然后安装所有依赖：

```bash
pip install -r requirements.txt
```

### 运行 MIS 系统

所有依赖安装完毕后，输入以下命令运行系统：

```bash
python manage.py migrate
python manage.py runserver
```

如果一切顺利，将会显示如下界面：

[![](https://static001.geekbang.org/resource/image/9a/81/9af6d454082c54db8cb27d1538f09281.jpg?wh=1940x458)](https://static001.geekbang.org/resource/image/9a/81/9af6d454082c54db8cb27d1538f09281.jpg?wh=1940x458)

系统启动成功

### 确认系统正常运行

打开浏览器，访问 `[http://127.0.0.1:8000/](http://127.0.0.1:8000/)`，应该会出现以下页面：

[![](https://static001.geekbang.org/resource/image/3a/32/3a7f5afcbba7e90e00c2f60b4b1e4c32.jpg?wh=1786x756)](https://static001.geekbang.org/resource/image/3a/32/3a7f5afcbba7e90e00c2f60b4b1e4c32.jpg?wh=1786x756)

MIS 系统首页

至此，MIS 系统可以正常运行了。

---

## 小结

> [!important]
>
> 这一讲我们学会了三件事：
>
> 1. **说服利益相关方**：讨论了如何说服利益相关方同意推动项目的 RAG 改造，并分析了改造的切入点
>
> 1. **改造前后对比**：展示了实战案例改造前后的模样，建立了感性、直观的认识
>
> 1. **环境搭建**：学习了如何把要改造的传统 MIS 系统运行起来，并搭建了整个课程所需的环境

下一节我们开始讲这个实战案例的第一个基础概念：**对话模式**。

---

## 思考题

> [!important]
>
> 既然一个 RAG 应用无法一步到位，那么我们如何度过 RAG 应用不成熟的早期阶段呢？

欢迎你在留言区交流互动，如果这节课对你有启发，也推荐分享给身边更多朋友。


课程二维码
