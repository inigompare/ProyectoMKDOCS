# Troubleshooting: Errors and Solutions

This is the most important section of the documentation. Here I document **the real errors** I encountered during the project development and how I solved them. Learning from errors is fundamental in systems administration.

![Troubleshooting](img/troubleshooting.png)

---

## 🔴 Problem 1: PowerShell Permissions

### Error Description

When trying to install packages with `pip` or run certain administration commands, PowerShell showed the following error:

!!! failure "Error: The requested operation requires elevation"

````
ERROR: Could not install packages due to an OSError: [WinError 5]
Access denied: 'C:\Program Files\Python312\Lib\site-packages\...'

    Consider using the `--user` option or check the permissions.
    ```

    Or the more direct message:

    ```
    The requested operation requires elevation.
    ```

### Problem Analysis

This error occurs because Windows protects system folders (like `C:\Program Files\`) and requires **administrator permissions** to modify them. When installing Python packages globally, `pip` tries to write to these protected folders.

### Solution

!!! success "Solution: Run PowerShell as Administrator"
    **Option A: Open terminal with elevated permissions**

    1. Search for "PowerShell" in the start menu
    2. Right-click → **Run as administrator**
    3. Confirm the UAC (User Account Control) dialog
    4. Run the command that failed before

    ![Run as administrator](img/run-as-admin.png)

=== "Option B: User Installation"

    If you don't have administrator permissions, you can install packages only for your user:

    ```powershell
    pip install --user mkdocs-material
    ```

    ⚠️ Note: This option may cause PATH issues.

=== "Option C: Virtual Environment"

    The cleanest option is to use a Python virtual environment:

    ```powershell
    # Create the virtual environment
    python -m venv venv

    # Activate the environment
    .\venv\Scripts\Activate

    # Install inside the environment
    pip install mkdocs-material
    ```

??? tip "Tip for VS Code"
    If you use VS Code, you can configure the integrated terminal to open PowerShell with administrator permissions by default. However, this is not recommended for security. It's better to open an external terminal when you need elevated permissions.

---

## 🔴 Problem 2: YAML Syntax Error

### Error Description

When running `mkdocs serve`, the system showed a parsing error in the configuration file:

!!! failure "Error: YAML Syntax Error"
    `     ERROR   -  Config file 'mkdocs.yml' could not be loaded:
               while parsing a block mapping
               expected <block end>, but found '<scalar>'
               in "mkdocs.yml", line 35, column 1
               could not find expected ':'
    `

### Problem Analysis

Reviewing the `mkdocs.yml` file, I discovered that I had made a serious error: **I had mixed SSH commands and YAML configuration in the same file**. Also, the indentation was inconsistent.

The corrupted file looked like this:

```yaml title="❌ mkdocs.yml (INCORRECT)"
site_name: My Project
theme:
  name: material

# Generate SSH key (THIS DOESN'T GO HERE)
ssh-keygen -t rsa -b 4096

nav:
- Home: index.md
   - Page 2: page2.md  # Wrong indentation
````

### Solution

!!! success "Solution: Clean and Format Correctly"
The YAML file must contain **only configuration**, not commands. Also, indentation must be consistent.

    ```yaml title="✅ mkdocs.yml (CORRECT)"
    site_name: My Project

    theme:
      name: material
      palette:
        primary: indigo

    nav:
      - Home: index.md
      - Page 2: page2.md
    ```

### Golden Rules for YAML

| Rule                                      | Correct Example                | Incorrect Example                |
| ----------------------------------------- | ------------------------------ | -------------------------------- |
| Use spaces, not tabs                      | `  name: value`                | `→ name: value`                  |
| 2-space indentation                       | `theme:`<br>`  name: material` | `theme:`<br>`    name: material` |
| Lists with dash and space                 | `- item`                       | `-item`                          |
| Strings with special characters in quotes | `title: "Hello: World"`        | `title: Hello: World`            |

??? warning "How to Detect Invisible Tabs"

    In VS Code, you can visualize invisible characters:

    1. Open the command palette (`Ctrl + Shift + P`)
    2. Search for "Toggle Render Whitespace"
    3. Spaces will appear as dots (·) and tabs as arrows (→)

    You can also configure VS Code to convert tabs to spaces automatically in YAML files.

---

## 🔴 Problem 3: Incomplete GitHub Pages Deployment

### Error Description

After running `mkdocs gh-deploy`, the GitHub Pages page showed a **404 error** or didn't update with the latest changes.

!!! failure "Error: Page Not Found (404)"
When accessing `https://your-user.github.io/Project-MKDOCS/` appeared:

    > **404 - There isn't a GitHub Pages site here.**

### Possible Causes and Solutions

=== "Cause 1: Wrong Branch"

    GitHub Pages may be configured to serve from the wrong branch.

    **Verify:**
    ```powershell
    git branch -a
    ```

    **Solution:**

    1. Go to your repository on GitHub
    2. Settings → Pages
    3. Make sure Source is set to `gh-pages` and `/root`

    ![GitHub Pages configuration](img/github-pages-settings.png)

=== "Cause 2: Browser Cache"

    Sometimes the browser caches the 404 page.

    **Solution:**

    - Do a hard refresh: `Ctrl + Shift + R`
    - Or open in an incognito window
    - Wait 2-3 minutes (GitHub Pages may take time to propagate)

=== "Cause 3: Deployment Not Completed"

    The `gh-deploy` command may have failed silently.

    **Verify:**
    ```powershell
    # View the last deployment
    git log gh-pages -1
    ```

    **Solution:**
    Deploy again forcing the update:
    ```powershell
    mkdocs gh-deploy --force
    ```

### Correct Deployment Command

```powershell
# Make sure you're on main branch with committed changes
git add .
git commit -m "Update documentation"
git push origin main

# Deploy to GitHub Pages
mkdocs gh-deploy
```

!!! success "Successful Deployment"
`     INFO    -  Cleaning site directory
    INFO    -  Building documentation to directory: site
    INFO    -  Documentation built in 0.82 seconds
    INFO    -  Copying 'site' to 'gh-pages' branch and pushing to GitHub.
    INFO    -  Your documentation should shortly be available at:
               https://your-user.github.io/Project-MKDOCS/
    `

---

## 🟡 Problem 4: Empty or Incomplete Content

### Problem Description

Initially, the `.md` files were practically empty or contained only plain text without formatting. The result was a functional but visually poor website.

### Analysis

The problem was the lack of knowledge about **Material for MkDocs** capabilities. I wasn't taking advantage of:

- Admonitions (colored alerts)
- Code blocks with syntax highlighting
- Tabs
- Collapsible blocks
- Tables
- Emojis and icons

### Solution

!!! success "Learn Extended Markdown Syntax"
Material for MkDocs extends Markdown with many extra features. The key is:

    1. **Read the official documentation**: [squidfunk.github.io/mkdocs-material](https://squidfunk.github.io/mkdocs-material/)
    2. **Enable the extensions** in `mkdocs.yml`
    3. **Practice** with each type of element

??? example "Syntax Cheatsheet"

    **Alerts:**
        `markdown
        !!! note "Title"
        Content
    `

    **Code with title:**
        ```markdown
        ```python title="example.py"
        print("Hello World")
        ```
        ```

    **Tabs:**
        ```markdown
        === "Tab 1"
        Content 1

        === "Tab 2"
            Content 2
        ```

    **Collapsible:**
        ```markdown
        ??? tip "Click to see more"
            Hidden content
        ```

---

## ✅ Lessons Learned

!!! quote "Final Reflection"
Every error was a learning opportunity. The most frustrating problems taught the most valuable lessons:

    - **Permissions**: Always verify you have the necessary permissions before running commands
    - **Syntax**: YAML is very demanding with format; use a validator or an editor with highlighting
    - **Deployment**: Read the complete logs, not just the error message
    - **Documentation**: Take time to learn the tools you use

[Go to Conclusions :material-arrow-right:](conclusiones.md){ .md-button .md-button--primary }
