
# Git and GitHub Command Cheat Sheet

## Setting Up Git
- **Check Git version**:
  ```bash
  git --version
  ```

- **Configure Git with your name and email**:
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "your_email@example.com"
  ```

- **View Git configuration**:
  ```bash
  git config --list
  ```

---

## Basic Git Commands

### Repository Initialization
- **Initialize a Git repository**:
  ```bash
  git init
  ```

- **Clone a repository**:
  ```bash
  git clone <repository_url>
  ```

### Staging and Committing Changes
- **Check repository status**:
  ```bash
  git status
  ```

- **Stage files for commit**:
  ```bash
  git add <file_name>
  git add .  # Stages all files
  ```

- **Commit changes**:
  ```bash
  git commit -m "Commit message"
  ```

- **Amend the last commit**:
  ```bash
  git commit --amend -m "Updated commit message"
  ```

### Viewing Changes and History
- **View commit history**:
  ```bash
  git log
  ```

- **View a concise log**:
  ```bash
  git log --oneline
  ```

- **View changes in a file**:
  ```bash
  git diff <file_name>
  ```

---

## Branching and Merging
- **Create a new branch**:
  ```bash
  git branch <branch_name>
  ```

- **Switch to a branch**:
  ```bash
  git checkout <branch_name>
  ```

- **Create and switch to a new branch**:
  ```bash
  git checkout -b <branch_name>
  ```

- **Merge a branch**:
  ```bash
  git merge <branch_name>
  ```

- **Delete a branch**:
  ```bash
  git branch -d <branch_name>
  ```

---

## Remote Repositories

### Connecting to GitHub
- **Add a remote repository**:
  ```bash
  git remote add origin <repository_url>
  ```

- **View remote repositories**:
  ```bash
  git remote -v
  ```

- **Push changes to a remote repository**:
  ```bash
  git push origin <branch_name>
  ```

- **Pull changes from a remote repository**:
  ```bash
  git pull origin <branch_name>
  ```

### Tags and Releases
- **Create a tag**:
  ```bash
  git tag -a v1.0 -m "Version 1.0"
  ```

- **Push a tag**:
  ```bash
  git push origin v1.0
  ```

- **List all tags**:
  ```bash
  git tag
  ```

---

## Undoing Changes
- **Unstage a file**:
  ```bash
  git reset <file_name>
  ```

- **Revert a commit**:
  ```bash
  git revert <commit_hash>
  ```

- **Reset to a previous commit**:
  ```bash
  git reset --hard <commit_hash>
  ```

---

## Advanced Commands

### Stashing Changes
- **Save changes for later**:
  ```bash
  git stash
  ```

- **Apply stashed changes**:
  ```bash
  git stash apply
  ```

- **List stashes**:
  ```bash
  git stash list
  ```

### Viewing and Fixing Conflicts
- **View merge conflicts**:
  ```bash
  git diff
  ```

- **Mark conflicts as resolved**:
  ```bash
  git add <file_name>
  ```

---

## Tips for GitHub
- Always write descriptive commit messages.
- Regularly pull changes from the remote repository to stay updated.
- Use `.gitignore` to exclude files/folders from being tracked by Git.
  Example `.gitignore`:
  ```
  __pycache__/
  *.log
  *.env
  ```

---

For more detailed documentation, visit the [Git Documentation](https://git-scm.com/doc).
