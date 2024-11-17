Here's a comprehensive set of notes for Labs 1, 2, and 3 in Markdown format, integrating key instructions and additional details to enhance understanding.

---

# ET0735 DevOps for AIoT

## Laboratory Notes

### Lab 1: Introduction to Git and GitHub

#### Objectives
- Understand and use Git for version control.
- Set up and configure Git and GitHub.
- Learn essential Git operations: commit, branch, tag, and push.

#### Procedures
1. **Git Installation**  
   - Install Git using [Git SCM](https://git-scm.com/download/win).
   - Configure user details:
     ```bash
     git config --global user.name "Your Name"
     git config --global user.email "your_email@example.com"
     ```
   - Verify configuration:
     ```bash
     git config --list
     ```

2. **Creating a Local Repository**  
   - Navigate to the desired folder:
     ```bash
     cd path/to/your/folder
     ```
   - Initialize Git:
     ```bash
     git init
     ```

3. **Committing Files**  
   - Add files to the staging area:
     ```bash
     git add filename
     ```
   - Commit changes:
     ```bash
     git commit -m "Your commit message"
     ```

4. **Branches and Merging**  
   - Create a branch:
     ```bash
     git branch branch_name
     ```
   - Switch to the branch:
     ```bash
     git checkout branch_name
     ```
   - Merge changes into `master`:
     ```bash
     git merge branch_name
     ```

5. **Pushing to GitHub**  
   - Add a remote:
     ```bash
     git remote add origin repository_url
     ```
   - Push to remote:
     ```bash
     git push -u origin master
     ```

#### Activities
- Create a GitHub repository and practice creating README.md files.
- Experiment with tags:
  ```bash
  git tag -a v1.0 -m "Initial Release"
  git push origin v1.0
  ```

---

### Lab 2: Introduction to Python

#### Objectives
- Implement Python programs with basic operations.
- Utilize functions, input/output, and list data structures.

#### Procedures
1. **Python and VS Code Installation**  
   - Install Python 3 from [python.org](https://www.python.org/downloads/).
   - Install VS Code from [Visual Studio Code](https://code.visualstudio.com/).

2. **Creating Python Projects**  
   - Create a project folder:
     ```bash
     mkdir Lab2
     cd Lab2
     ```
   - Open the folder in VS Code and add a Python file, e.g., `Lab2.py`.

3. **Python Basics**
   - Write a basic Python script:
     ```python
     print("ET0735 - Lab 2 - Introduction to Python")
     ```
   - Run the script in VS Code.

4. **Implementing BMI Calculation**  
   - Function implementation:
     ```python
     def calculate_bmi(height, weight):
         bmi = weight / (height ** 2)
         return bmi
     ```

5. **GitHub Integration**
   - Add and push changes to GitHub following the Lab 1 workflow.

---

### Lab 3: Developing Software Unit Tests

#### Objectives
- Learn to write and run unit tests using PyTest.

#### Procedures
1. **PyTest Setup**  
   - Install PyTest:
     ```bash
     pip install pytest
     ```
   - Configure PyTest in VS Code.

2. **Writing Test Cases**  
   - Create a test file, e.g., `Test_Lab3.py`:
     ```python
     import pytest
     from Lab3 import bubble_sort

     def test_bubble_sort_ascending():
         assert bubble_sort([3, 2, 1], "asc") == [1, 2, 3]
     ```

3. **Executing Tests**  
   - Run all tests:
     ```bash
     pytest
     ```
   - View results in the VS Code Testing tab.

4. **Integrating with Lab 2 Code**  
   - Import and test BMI functionality:
     ```python
     from Lab2.bmi import calculate_bmi

     def test_bmi_underweight():
         assert calculate_bmi(1.7, 50) == -1
     ```

5. **GitHub Integration**  
   - Add and commit test cases:
     ```bash
     git add .
     git commit -m "Add unit tests"
     git push
     ```

---

### Additional Hints and Best Practices

#### Markdown Formatting
- Use headings (`#`, `##`, `###`) to organize content.
- Embed code blocks with backticks (` ``` `).
- Add lists:
  - Unordered: `- Item`
  - Ordered: `1. Item`
- Include links and images:
  ```markdown
  [Python Docs](https://www.python.org/doc/)
  ![Example](path/to/image.png)
  ```

#### Focus Areas
- Exercise 4 and 5 from Lab 3 are crucial. Practice using PyTest assertions extensively.

---

This `.md` file format provides structured and detailed lab notes for easy reference and future use.