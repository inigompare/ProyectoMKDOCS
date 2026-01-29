# 结论

本项目是一个完整的实践练习，涵盖了 ASIR 课程的多项能力。除了创建一个简单的网站外，我还了解了 **技术文档** 和 **基础设施即代码 (IaC)** 范式的重要性。

![结论](img/conclusiones.png)

---

## 📝 关于文档的思考

### 为什么文档如此重要？

技术文档不是“额外的东西”，它是系统管理员工作的基本组成部分。好处显而易见：

!!! quote "文档是你给未来的自己的一份礼物" - **可复现性**：能够在几个月后重复该过程 - **协作**：允许他人理解和改进你的工作 - **调试**：记住你做了什么以及为什么这样做 - **专业性**：展示严谨和有条理的工作

### 文档即代码 (Docs as Code)

本项目体现了 **"Docs as Code"** 的概念：

| 方面     | 传统方式   | 文档即代码 (Docs as Code)  |
| -------- | ---------- | -------------------------- |
| 格式     | Word, PDF  | Markdown, reStructuredText |
| 版本控制 | 无         | Git                        |
| 协作     | 发送文件   | Pull Requests (拉取请求)   |
| 发布     | 手动       | 自动 CI/CD                 |
| 托管     | 自有服务器 | GitHub Pages (免费)        |

??? tip "基础设施即代码 (IaC)"

    同样的原则也适用于基础设施。不再手动配置服务器，而是编写定义系统所需状态的配置文件（Terraform, Ansible, Docker）。

    优势：

    - **可版本化**：完整的变更历史
    - **可复制**：在任何环境中相同的配置
    - **可自动化**：无需人工干预即可部署
    - **可审计**：知道谁在何时更改了什么

---

## 🌐 GitHub Pages vs 传统托管

### GitHub Pages 的优势

| 特性            | GitHub Pages                     | 传统托管           |
| --------------- | -------------------------------- | ------------------ |
| **成本**        | 免费                             | 最低 5-20€/月      |
| **SSL (HTTPS)** | 自动包含                         | 必须配置           |
| **CDN**         | 包含 (Fastly)                    | 额外或手动         |
| **维护**        | 零                               | 更新、备份...      |
| **部署**        | `git push` 或 `mkdocs gh-deploy` | FTP, SSH, 控制面板 |
| **可扩展性**    | 自动                             | 取决于计划         |

### GitHub Pages 的限制

!!! warning "并非一切都很完美"
GitHub Pages 有一些需要牢记的限制：

    - **仅静态站点**：不支持 PHP、Python 后端、数据库...
    - **大小限制**：每个仓库最大 1GB
    - **带宽**：100GB/月限制（对于文档来说绰绰有余）
    - **每小时构建数**：每小时最多 10 次构建
    - **自定义域名**：需要额外的 DNS 配置

### 何时使用每种选项？

=== "使用 GitHub Pages"

    ✅ 技术文档

    ✅ 作品集和在线简历

    ✅ 静态博客（使用 Jekyll, Hugo, MkDocs）

    ✅ 开源项目

    ✅ 简单的着陆页

=== "使用传统托管"

    ✅ 动态 Web 应用程序（商店、论坛）

    ✅ 带数据库的站点

    ✅ 具有特定服务器要求的项目

    ✅ 当你需要完全的服务器控制权时

    ✅ 对于需要特定 SLA 的客户

---

## 🎓 开发的能力

在本项目中，我练习了 ASIR 课程的以下能力：

- [x] **CLI 和 PowerShell**：导航、包安装、权限管理
- [x] **版本控制**：Git (add, commit, push, branch)
- [x] **标记语言**：Markdown, YAML
- [x] **解决问题**：错误调试、日志阅读
- [x] **云和托管**：GitHub Pages, 概念性 DNS
- [x] **技术文档**：清晰的写作、结构、专业格式

---

## 📚 参考文献和资源

### 官方文档

- **MkDocs**: [mkdocs.org](https://www.mkdocs.org/)
- **Material for MkDocs**: [squidfunk.github.io/mkdocs-material](https://squidfunk.github.io/mkdocs-material/)
- **GitHub Pages**: [pages.github.com](https://pages.github.com/)
- **Python**: [python.org](https://www.python.org/)
- **Git**: [git-scm.com/doc](https://git-scm.com/doc)

### 推荐教程

??? info "额外资源"

    **视频：**

    - [MkDocs 教程 - TechWorld with Nana](https://www.youtube.com/watch?v=Q-YA_dA8C20)
    - [Git 和 GitHub 初学者教程 - freeCodeCamp](https://www.youtube.com/watch?v=RGOj5yH7evk)

    **文章：**

    - [MkDocs Python 项目文档入门](https://realpython.com/python-project-documentation-with-mkdocs/)
    - [GitHub Pages 文档](https://docs.github.com/en/pages)

    **工具：**

    - [YAML 验证器](https://www.yamllint.com/) - 验证 YAML 文件
    - [Markdown 预览](https://markdownlivepreview.com/) - 预览 Markdown

---

## 🏁 结语

!!! success "项目完成"
本网站是所学一切的有形证明。从最初的 Python 安装到最终在 GitHub Pages 上部署，每一步都已被记录下来，以供将来参考。

    ASIR 课程让我们准备好管理复杂的基础设施，而像这样的项目表明，即使是像静态站点生成器这样“简单”的工具，也能教会我们很多关于最佳实践、问题解决和专业精神的知识。

---

<div style="text-align: center; margin-top: 2rem;">
    <p><strong>为 SRI 科目制作的项目</strong></p>
    <p>ASIR - ILERNA | 2026</p>
</div>
