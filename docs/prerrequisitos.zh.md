# 环境准备

在创建 MkDocs 站点之前，我们需要准备开发环境。本节涵盖了在 **Windows** 系统上安装所有必要工具的内容。

![环境准备](img/preparacion.png)

## 📋 先决条件

要遵循本指南，你需要：

- **Windows 10/11** 操作系统
- 互联网连接
- 计算机的管理员权限

---

## 1️⃣ Python 安装

Python 是运行 MkDocs 的编程语言。

### 下载

1. 前往官方网站：[python.org/downloads](https://www.python.org/downloads/)
2. 下载最新的稳定版本（3.12 或更高版本）

### 安装

!!! warning "关键步骤"
在安装过程中，**勾选** `Add Python to PATH`（将 Python 添加到 PATH）复选框。如果你忘记这一步，Python 命令将在终端中无法工作。

![Python 安装](img/python-install.png)

### 验证

打开 **PowerShell** 并运行：

```powershell
python --version
```

你应该看到类似的内容：

```
Python 3.12.1
```

??? question "命令不工作？"
如果你看到类似 `python: command not found` 的错误，这意味着 Python 不在 PATH 中。你可以：

    1. 重新安装 Python 并勾选 "Add to PATH" 复选框
    2. 或者手动将 Python 添加到系统环境变量中

---

## 2️⃣ Git 安装

Git 对于版本控制和部署到 GitHub Pages 至关重要。

### 下载

1. 前往：[git-scm.com/download/win](https://git-scm.com/download/win)
2. 下载 64 位安装程序

### 安装

=== "推荐选项"

    在安装向导中，选择：

    - **默认编辑器**：Visual Studio Code
    - **PATH 环境**：Git from the command line and also from 3rd-party software
    - **HTTPS 传输后端**：Use the OpenSSL library
    - **行尾转换**：Checkout Windows-style, commit Unix-style

=== "快速安装"

    如果你喜欢快速安装，只需在所有选项上点击 "Next"（下一步），默认值是足够的。

### 验证

```powershell
git --version
```

预期结果：

```
git version 2.43.0.windows.1
```

### Git 初始配置

配置你的身份（提交所需）：

```powershell
git config --global user.name "你的名字"
git config --global user.email "your.email@example.com"
```

---

## 3️⃣ MkDocs 和 Material 安装

现在我们安装 MkDocs 以及 Material 主题，它包含了我们将使用的所有高级功能。

### 安装命令

```powershell
pip install mkdocs-material
```

!!! success "为什么是 `mkdocs-material` 而不仅仅是 `mkdocs`？"
`mkdocs-material` 包会自动包含 MkDocs 作为依赖项，加上 Material 主题及其所有扩展。这是安装所有内容的最有效方式。

### 安装验证

```powershell
mkdocs --version
```

预期结果：

```
mkdocs, version 1.6.0 from C:\Users\...\site-packages\mkdocs (Python 3.12)
```

---

## 4️⃣ GitHub 仓库设置

### 创建仓库

1. 前往 [github.com](https://github.com) 并登录
2. 点击 **New repository**（新建仓库）
3. 配置：
   - **Repository name**（仓库名称）：`Project-MKDOCS`
   - **Description**（描述）：`Technical documentation with MkDocs`
   - **Visibility**（可见性）：Public（公共，免费 GitHub Pages 所需）
   - **Initialize with**（初始化）：不勾选任何选项

![在 GitHub 上创建仓库](img/github-new-repo.png)

### 克隆仓库

```powershell
cd C:\Users\你的用户\Desktop\ASIR
git clone https://github.com/your-user/Project-MKDOCS.git
cd Project-MKDOCS
```

---

## ✅ 验证总结

在继续之前，确保所有命令都能工作：

```powershell
# 验证 Python
python --version

# 验证 pip
pip --version

# 验证 Git
git --version

# 验证 MkDocs
mkdocs --version
```

!!! success "环境就绪！"
如果所有命令都正确返回了版本，你的环境就准备好创建 MkDocs 项目了。

[继续进行配置 :material-arrow-right:](estructura.md){ .md-button .md-button--primary }
