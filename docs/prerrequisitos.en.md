# Environment Setup

Before we can create our MkDocs site, we need to prepare the development environment. This section covers the installation of all necessary tools on a **Windows** system.

![Environment setup](img/preparacion.png)

## 📋 Prerequisites

To follow this guide you will need:

- **Windows 10/11** operating system
- Internet connection
- Administrator permissions on the computer

---

## 1️⃣ Python Installation

Python is the programming language on which MkDocs runs.

### Download

1. Go to the official website: [python.org/downloads](https://www.python.org/downloads/)
2. Download the latest stable version (3.12 or higher)

### Installation

!!! warning "Critical Step"
During installation, **check the box** `Add Python to PATH`. If you forget this, Python commands will not work from the terminal.

![Python Installation](img/python-install.png)

### Verification

Open **PowerShell** and run:

```powershell
python --version
```

You should see something like:

```
Python 3.12.1
```

??? question "Command not working?"
If you see an error like `python: command not found`, it means Python is not in the PATH. You can:

    1. Reinstall Python checking the "Add to PATH" box
    2. Or manually add Python to the system environment variables

---

## 2️⃣ Git Installation

Git is essential for version control and for deployment to GitHub Pages.

### Download

1. Go to: [git-scm.com/download/win](https://git-scm.com/download/win)
2. Download the 64-bit installer

### Installation

=== "Recommended Options"

    During the installation wizard, select:

    - **Default editor**: Visual Studio Code
    - **PATH environment**: Git from the command line and also from 3rd-party software
    - **HTTPS transport backend**: Use the OpenSSL library
    - **Line ending conversions**: Checkout Windows-style, commit Unix-style

=== "Quick Installation"

    If you prefer a quick installation, simply click "Next" on all options, the default values are adequate.

### Verification

```powershell
git --version
```

Expected result:

```
git version 2.43.0.windows.1
```

### Initial Git Configuration

Configure your identity (required for commits):

```powershell
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

---

## 3️⃣ MkDocs and Material Installation

Now we install MkDocs along with the Material theme, which includes all the advanced features we will use.

### Installation Command

```powershell
pip install mkdocs-material
```

!!! success "Why `mkdocs-material` and not just `mkdocs`?"
The `mkdocs-material` package automatically includes MkDocs as a dependency, plus the Material theme with all its extensions. It's the most efficient way to install everything.

### Installation Verification

```powershell
mkdocs --version
```

Expected result:

```
mkdocs, version 1.6.0 from C:\Users\...\site-packages\mkdocs (Python 3.12)
```

---

## 4️⃣ GitHub Repository Setup

### Create the Repository

1. Go to [github.com](https://github.com) and sign in
2. Click on **New repository**
3. Configure:
   - **Repository name**: `Project-MKDOCS`
   - **Description**: `Technical documentation with MkDocs`
   - **Visibility**: Public (required for free GitHub Pages)
   - **Initialize with**: Don't check any option

![Create repository on GitHub](img/github-new-repo.png)

### Clone the Repository

```powershell
cd C:\Users\YourUser\Desktop\ASIR
git clone https://github.com/your-user/Project-MKDOCS.git
cd Project-MKDOCS
```

---

## ✅ Verification Summary

Before continuing, make sure all commands work:

```powershell
# Verify Python
python --version

# Verify pip
pip --version

# Verify Git
git --version

# Verify MkDocs
mkdocs --version
```

!!! success "Environment Ready!"
If all commands return their version correctly, your environment is ready to create the MkDocs project.

[Continue with Configuration :material-arrow-right:](estructura.md){ .md-button .md-button--primary }
