# Conclusions

This project has been a complete practical exercise covering multiple competencies of the ASIR program. Beyond creating a simple website, I have learned about the importance of **technical documentation** and the **Infrastructure as Code (IaC)** paradigm.

![Conclusions](img/conclusiones.png)

---

## 📝 Reflection on Documentation

### Why is documenting so important?

Technical documentation is not an "extra", it is a fundamental part of a system administrator's work. The benefits are clear:

!!! quote "Documentation is a gift you give to your future self" - **Reproducibility**: Being able to repeat a process months later - **Collaboration**: Allowing others to understand and improve your work - **Debugging**: Remembering what you did and why you did it - **Professionalism**: Demonstrating rigorous and organized work

### Documentation as Code

This project exemplifies the concept of **"Docs as Code"**:

| Aspect          | Traditional | Docs as Code               |
| --------------- | ----------- | -------------------------- |
| Format          | Word, PDF   | Markdown, reStructuredText |
| Version control | None        | Git                        |
| Collaboration   | Send files  | Pull Requests              |
| Publication     | Manual      | Automatic CI/CD            |
| Hosting         | Own server  | GitHub Pages (free)        |

??? tip "Infrastructure as Code (IaC)"

    The same principle applies to infrastructure. Instead of configuring servers manually, configuration files are written (Terraform, Ansible, Docker) that define the desired state of the system.

    Advantages:

    - **Versionable**: Complete history of changes
    - **Replicable**: Same configuration in any environment
    - **Automatable**: Deployment without manual intervention
    - **Auditable**: Know who changed what and when

---

## 🌐 GitHub Pages vs Traditional Hosting

### Advantages of GitHub Pages

| Feature         | GitHub Pages                     | Traditional Hosting     |
| --------------- | -------------------------------- | ----------------------- |
| **Cost**        | Free                             | Minimum 5-20€/month     |
| **SSL (HTTPS)** | Automatically included           | Must configure it       |
| **CDN**         | Included (Fastly)                | Extra or manual         |
| **Maintenance** | Zero                             | Updates, backups...     |
| **Deployment**  | `git push` or `mkdocs gh-deploy` | FTP, SSH, control panel |
| **Scalability** | Automatic                        | Depends on plan         |

### GitHub Pages Limitations

!!! warning "Not everything is perfect"
GitHub Pages has some limitations to keep in mind:

    - **Static sites only**: Does not support PHP, Python backend, databases...
    - **Size limit**: Maximum 1GB per repository
    - **Bandwidth**: 100GB/month limit (more than enough for documentation)
    - **Builds per hour**: Maximum 10 builds/hour
    - **Custom domain**: Requires additional DNS configuration

### When to use each option?

=== "Use GitHub Pages"

    ✅ Technical documentation

    ✅ Portfolios and online resumes

    ✅ Static blogs (with Jekyll, Hugo, MkDocs)

    ✅ Open source projects

    ✅ Simple landing pages

=== "Use Traditional Hosting"

    ✅ Dynamic web applications (stores, forums)

    ✅ Sites with databases

    ✅ Projects with specific server requirements

    ✅ When you need total server control

    ✅ For clients requiring specific SLAs

---

## 🎓 Developed Competencies

During this project I have practiced the following competencies of the ASIR program:

- [x] **CLI and PowerShell**: Navigation, package installation, permission management
- [x] **Version control**: Git (add, commit, push, branch)
- [x] **Markup languages**: Markdown, YAML
- [x] **Problem solving**: Error debugging, log reading
- [x] **Cloud and hosting**: GitHub Pages, conceptual DNS
- [x] **Technical documentation**: Clear writing, structure, professional format

---

## 📚 Bibliography and Resources

### Official Documentation

- **MkDocs**: [mkdocs.org](https://www.mkdocs.org/)
- **Material for MkDocs**: [squidfunk.github.io/mkdocs-material](https://squidfunk.github.io/mkdocs-material/)
- **GitHub Pages**: [pages.github.com](https://pages.github.com/)
- **Python**: [python.org](https://www.python.org/)
- **Git**: [git-scm.com/doc](https://git-scm.com/doc)

### Recommended Tutorials

??? info "Additional Resources"

    **Videos:**

    - [MkDocs Tutorial - TechWorld with Nana](https://www.youtube.com/watch?v=Q-YA_dA8C20)
    - [Git and GitHub for Beginners - freeCodeCamp](https://www.youtube.com/watch?v=RGOj5yH7evk)

    **Articles:**

    - [Getting Started with MkDocs](https://realpython.com/python-project-documentation-with-mkdocs/)
    - [GitHub Pages Documentation](https://docs.github.com/en/pages)

    **Tools:**

    - [YAML Validator](https://www.yamllint.com/) - To validate YAML files
    - [Markdown Preview](https://markdownlivepreview.com/) - To preview Markdown

---

## 🏁 Closing

!!! success "Project Completed"
This website is tangible proof of everything learned. From the initial Python installation to the final deployment on GitHub Pages, every step has been documented to serve as a future reference.

    The ASIR program prepares us to manage complex infrastructures, and projects like this demonstrate that even "simple" tools like a static site generator can teach us a lot about best practices, problem solving and professionalism.

---

<div style="text-align: center; margin-top: 2rem;">
    <p><strong>Project made for the SRI subject</strong></p>
    <p>ASIR - ILERNA | 2026</p>
</div>
