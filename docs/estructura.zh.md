# 项目配置

工具安装完成后，就可以创建和配置我们的 MkDocs 项目了。在本节中，你将了解文件结构以及主配置文件的通过方式。

![项目结构](img/estructura.png)

---

## 1️⃣ 创建基础项目

### 初始化 MkDocs

导航到你的项目文件夹并运行初始化命令：

```powershell
cd C:\Users\你的用户\Desktop\ASIR\Project-MKDOCS
mkdocs new .
```

!!! info "`mkdocs new .` 做什么？"
此命令在当前目录（`.`）中创建基本项目结构：

    - `mkdocs.yml` - 主配置文件
    - `docs/` - Markdown 文件文件夹
    - `docs/index.md` - 默认主页

###生成的结构

```
Project-MKDOCS/
├── docs/
│   └── index.md
└── mkdocs.yml
```

---

## 2️⃣ mkdocs.yml 文件

`mkdocs.yml` 文件是项目的 **核心**。一切都在这里配置：主题、扩展、导航和站点元数据。

### 文件解剖

```yaml title="mkdocs.yml"
# ============================================
# 站点元数据
# ============================================
site_name: MkDocs Meta-Documentation
site_description: 部署 MkDocs 的分步指南
site_author: ASIR 学生

# ============================================
# 主题和外观
# ============================================
theme:
  name: material
  language: en
  palette:
    primary: indigo
    accent: indigo

# ============================================
# MARKDOWN 扩展
# ============================================
markdown_extensions:
  - admonition
  - pymdownx.details
  - pymdownx.superfences
  - pymdownx.tabbed:
      alternate_style: true
  - pymdownx.highlight:
      anchor_linenums: true

# ============================================
# 导航
# ============================================
nav:
  - 首页: index.md
  - 设置: prerrequisitos.md
  - 配置: estructura.md
  - 错误: problemas.md
  - 结论: conclusiones.md
```

!!! warning "YAML 语法：注意缩进！"
YAML 对空格非常敏感。你必须使用 **空格，绝不要用制表符 (Tab)**，并保持一致的缩进（通常为 2 个空格）。

    ```yaml
    # ✅ 正确
    theme:
      name: material
      palette:
        primary: indigo

    # ❌ 错误（制表符或错误的缩进）
    theme:
    	name: material
       palette:
        primary: indigo
    ```

---

## 3️⃣ 扩展解释

### Admonitions (提示框)

Admonitions 是用于突出显示重要信息的彩色框：

=== "代码"

    ```markdown
    !!! note "注意标题"
        注意内容。

    !!! warning "警告"
        这很重要。

    !!! success "成功"
        一切顺利！

    !!! failure "错误"
        出错了。
    ```

=== "结果"

    !!! note "注意标题"
        注意内容。

    !!! warning "警告"
        这很重要。

    !!! success "成功"
        一切顺利！

    !!! failure "错误"
        出错了。

### 可折叠块

对于并非每个人都需要看到的附加信息很有用：

=== "代码"

    ```markdown
    ??? tip "点击展开"
        此内容默认隐藏。

    ???+ note "默认展开"
        此块开始时是打开的。
    ```

=== "结果"

    ??? tip "点击展开"
        此内容默认隐藏。

    ???+ note "默认展开"
        此块开始时是打开的。

### 选项卡

非常适合展示替代方案或不同的操作系统：

=== "代码"

    ```markdown
    === "Windows"
        ```powershell
        pip install mkdocs-material
        ```

    === "Linux/Mac"
        ```bash
        pip3 install mkdocs-material
        ```
    ```

=== "结果"

    === "Windows"
        ```powershell
        pip install mkdocs-material
        ```

    === "Linux/Mac"
        ```bash
        pip3 install mkdocs-material
        ```

---

## 4️⃣ 预览站点

MkDocs 包含一个开发服务器，允许你实时查看更改。

### 启动服务器

```powershell
mkdocs serve
```

### 预期输出

```
INFO    -  Building documentation...
INFO    -  Cleaning site directory
INFO    -  Documentation built in 0.50 seconds
INFO    -  [12:30:45] Watching paths for changes: 'docs', 'mkdocs.yml'
INFO    -  [12:30:45] Serving on http://127.0.0.1:8000/
```

!!! success "服务器激活！"
打开浏览器并导航到 **http://127.0.0.1:8000** 以查看你的站点。你对文件所做的任何更改都会自动反映出来。

### 停止服务器

在终端中按 `Ctrl + C` 停止服务器。

---

## 5️⃣ 添加新页面

要创建新页面：

1. 在 `docs/` 文件夹中创建一个 `.md` 文件
2. 在 `mkdocs.yml` 的 `nav` 部分添加条目

### 示例

```powershell
# 创建文件
New-Item -Path .\docs\new-page.md -ItemType File
```

```yaml title="mkdocs.yml"
nav:
  - 首页: index.md
  - 新页面: new-page.md
```

---

## ✅ 验证

要验证所有配置是否正确：

```powershell
# 验证配置
mkdocs build --strict
```

!!! success "构建成功"
如果命令完成且没有错误，则你的配置是正确的，站点已准备好部署。

[查看遇到的问题 :material-arrow-right:](problemas.md){ .md-button .md-button--primary }
