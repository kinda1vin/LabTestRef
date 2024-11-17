# ET0735 - DevOps for AIoT

## Laboratory 1: Introduction to Git and GitHub

### Objectives

By the end of this lab, you will:

- Perform Configuration Management using Git/GitHub workflows.
- Implement basic Git command-line operations such as:
  - Creating a new Git repository.
  - Committing files.
  - Creating and switching between branches.
- Set up a GitHub account and connect it to a remote repository.
- Push files from local to remote repositories.
- Create Git submodules to reference external repositories.

---

## Activities

### Git Installation and Setup
1. **Pre-requisites**: Ensure `.NET Framework 4.7 or later` is installed.
2. Download and run the [Git Installer](https://git-scm.com/download/win).
3. Configure Git with the following commands:
   ```bash
   git config --global user.name "<Your Name>"
   git config --global user.email "<Your Email>"
   git config --list
   ```

### Repository Setup
1. Create a new folder for the repository:
   ```bash
   mkdir <repository_name>
   cd <repository_name>
   git init
   ```

2. Verify initialization by observing the hidden `.git` folder.

### File Commit Workflow
1. Add a file (`HelloWorld.py`) and check its status:
   ```bash
   git status
   ```
2. Stage and commit the file:
   ```bash
   git add HelloWorld.py
   git commit -m "Initial version of HelloWorld"
   ```

---

## Key Git Commands

### Branching
- Create and list branches:
  ```bash
  git branch <branch_name>
  git branch
  ```
- Switch branches:
  ```bash
  git checkout <branch_name>
  ```

### Merging
- Merge branches:
  ```bash
  git merge <source_branch>
  ```

---

## Creating a GitHub Repository

1. Sign up for a [GitHub account](https://github.com).
2. Create a new repository and make it public.
3. Link the local repository to the remote GitHub repository:
   ```bash
   git remote add origin <repository_url>
   git push --set-upstream origin master
   ```

---

## GitHub Readme

Create a `README.md` file with the following content:
```markdown
# ET0735 - Lab 1 (Introduction to Git and GitHub)
This repository contains all the activities and configurations for Lab 1.
```

Push it to GitHub:
```bash
git add README.md
git commit -m "Added README file"
git push
```

---

## Advanced Git Features

### Tags and Releases
1. Add a tag:
   ```bash
   git tag -a v1.0 -m "Initial release"
   git push origin v1.0
   ```
2. Create a release from the GitHub interface.

### Submodules
1. Add an external repository as a submodule:
   ```bash
   git submodule add <repository_url>
   git submodule init
   git submodule update
   ```

---

## Hints for Lab 3 Exercises

### Focus Areas
- Practice **Exercises 4 and 5** from Lab 3.
- Pay particular attention to implementing **pytest** for these exercises.

### Testing with Pytest
- Create a `test_` file for each module you are testing.
- Example:
  ```python
  def test_function():
      assert function_to_test() == expected_value
  ```
- Use `pytest` to validate the tests:
  ```bash
  pytest <test_file.py>
  ```

---

## Markdown Formatting Techniques

### Headings
- Use `#`, `##`, `###` for headings.
  ```markdown
  # Main Heading
  ## Subheading
  ### Sub-subheading
  ```

### Code Blocks
- Wrap code with triple backticks (\`\`\`) and specify the language for syntax highlighting.
  ```python
  print("Hello, World!")
  ```

### Lists
- **Unordered** lists:
  ```markdown
  - Item 1
  - Item 2
  ```
- **Ordered** lists:
  ```markdown
  1. Step 1
  2. Step 2
  ```

### Tables
- Create tables using pipes (`|`) and dashes (`-`):
  ```markdown
  | Column 1 | Column 2 |
  |----------|----------|
  | Value 1  | Value 2  |
  ```

### Embedding Images
- Add images:
  ```markdown
  ![Alt text](image_url)
  ```

### Links
- Add hyperlinks:
  ```markdown
  [Link Text](url)
  ```

---

## Recommended Tools
- [Markdown Syntax Guide](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
- [Pytest Documentation](https://docs.pytest.org/en/stable/)

---