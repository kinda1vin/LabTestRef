Here’s the **Lab 1** content in `.md` format designed to serve as your notes:

```markdown
# ET0735 – Lab 1 (Introduction to Git and GitHub)

## Objectives
- Learn Git/GitHub workflow for configuration management.
- Perform Git operations:
  - Initialize a Git repository.
  - Commit changes.
  - Create and manage branches.
- Set up a GitHub account and push to a remote repository.
- Work with Git submodules.

## Activities
### 1. Installation and Setup
- Ensure .NET Framework (4.7+) is installed.
- Download Git: [Git SCM](https://git-scm.com/download/win).
- Configure Git user:
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  git config --list
  ```

### 2. Creating a Local Repository
- Create a new directory:
  ```bash
  mkdir Local_Git_Repository
  cd Local_Git_Repository
  git init
  ```

### 3. Committing Files
- Create a Python file `HelloWorld.py`:
  ```python
  print("Hello World!")
  ```
- Add to the staging area:
  ```bash
  git add HelloWorld.py
  ```
- Commit changes:
  ```bash
  git commit -m "Initial commit: Added HelloWorld.py"
  ```

### 4. Branch Management
- List branches:
  ```bash
  git branch
  ```
- Create and switch to a new branch:
  ```bash
  git branch bug-fix1
  git checkout bug-fix1
  ```

### 5. Pushing to GitHub
- Add a remote repository:
  ```bash
  git remote add origin https://github.com/<your-username>/<repo-name>.git
  ```
- Push changes:
  ```bash
  git push --set-upstream origin master
  ```

### 6. README.md Creation
- Create a `README.md` file with Markdown syntax:
  ```markdown
  # ET0735 – Lab 1 (Introduction to Git and GitHub)
  ```
- Commit and push the README to GitHub.

### 7. Tags and Releases
- Add a tag:
  ```bash
  git tag -a v1.0 -m "Initial release"
  git push origin v1.0
  ```

### 8. Git Submodules
- Add a submodule:
  ```bash
  git submodule add <repository-url>
  ```
- Commit and push changes:
  ```bash
  git add .gitmodules
  git commit -m "Added submodule"
  git push
  ```

## Notes
- Use `git diff` to compare changes.
- Experiment with:
  - Markdown for formatting.
  - Embedding links and images in your README.

## Hints
- Focus on **exercises 4 and 5** from Lab 3 for `pytest` implementation.
- Practice Markdown formatting:
  - Code blocks: \`\`\`
  - Lists: `-` or `1.`
  - Headings: `#`, `##`, etc.
  - Links: `[text](URL)`
```

Save the above text in a file named `README.md` to act as your notes for Lab 1.