# ET0735 Lab Notes - DevOps for AIoT

This document consolidates all the detailed instructions, procedures, and notes from the three labs conducted in ET0735 - DevOps for AIoT.

---

## Lab 1: Introduction to Git and GitHub

### Objectives
- Perform configuration management using Git/GitHub workflows.
- Execute basic Git operations: creating repositories, committing files, branching, and tagging.
- Push local repositories to GitHub and manage remote repositories.
- Create Git submodules for referencing external repositories.

### Procedures

1. **Installation and Setup**
   - Install Git from [git-scm.com](https://git-scm.com/download/win).
   - Configure user details:
     ```bash
     git config --global user.name "Your Name"
     git config --global user.email "Your Email"
     ```
   - Verify installation:
     ```bash
     git config --list
     ```

2. **Creating a Local Repository**
   - Create a folder for your repository:
     ```bash
     mkdir Local_Git_Repository
     cd Local_Git_Repository
     mkdir lab1
     cd lab1
     ```
   - Initialize the Git repository:
     ```bash
     git init
     ```

3. **Adding and Committing Files**
   - Create a file (e.g., `HelloWorld.py`) and write Python code.
   - Add the file to staging:
     ```bash
     git add HelloWorld.py
     ```
   - Commit the file:
     ```bash
     git commit -m "Initial version of HelloWorld.py"
     ```

4. **Working with Branches**
   - Create a branch:
     ```bash
     git branch bug-fix1
     ```
   - Switch to the new branch:
     ```bash
     git checkout bug-fix1
     ```
   - Merge the branch:
     ```bash
     git checkout master
     git merge bug-fix1
     ```

5. **Pushing to GitHub**
   - Create a GitHub repository and copy its URL.
   - Link the remote repository:
     ```bash
     git remote add origin <repository-url>
     ```
   - Push changes:
     ```bash
     git push -u origin master
     ```

6. **Tagging and Releases**
   - Tag a version:
     ```bash
     git tag -a v1.0 -m "Release v1.0"
     ```
   - Push the tag:
     ```bash
     git push origin v1.0
     ```

7. **Creating Submodules**
   - Add a submodule from another repository:
     ```bash
     git submodule add <repo-url>
     ```
   - Commit submodule changes:
     ```bash
     git add .
     git commit -m "Added submodule"
     git push
     ```

---

## Lab 2: Introduction to Python

### Objectives
- Set up Python development environment with Visual Studio Code.
- Implement basic Python functions, logical operators, and data processing.
- Integrate Python projects with Git/GitHub.

### Procedures

1. **Installation**
   - Install Python 3.11.x or later from [python.org](https://www.python.org/downloads/).
   - Install Visual Studio Code from [code.visualstudio.com](https://code.visualstudio.com/).

2. **Python Development**
   - Set up a new project folder (e.g., `Lab2`) inside `Local_Git_Repository`.
   - Create and execute Python scripts, e.g.:
     ```python
     print("ET0735 - Lab 2 - Introduction to Python")
     ```

3. **BMI Calculator**
   - Implement the `calculate_bmi` function:
     ```python
     def calculate_bmi(height, weight):
         bmi = weight / (height ** 2)
         if bmi < 18.5:
             return -1  # Underweight
         elif 18.5 <= bmi <= 25:
             return 0  # Normal weight
         else:
             return 1  # Overweight
     ```
   - Add classification logic for BMI ranges:
     - BMI < 18.5: Underweight.
     - 18.5 ≤ BMI ≤ 25: Normal weight.
     - BMI > 25: Overweight.

4. **Push to GitHub**
   - Commit the Python files:
     ```bash
     git add .
     git commit -m "Added BMI calculator"
     ```
   - Tag and push changes:
     ```bash
     git tag -a Lab2_v1.0 -m "Lab 2 release"
     git push origin Lab2_v1.0
     ```

---

## Lab 3: Developing Software Unit Tests

### Objectives
- Write and execute unit tests with PyTest.
- Validate Python functions implemented in Lab 2.
- Use Python dictionaries and lists for data manipulation.

### Exercises

#### **Exercise 4: Python Dictionaries**
1. **Using Dictionaries**:
   - Example:
     ```python
     fruits = {"apple": 2.5, "banana": 1.2}
     print(fruits["apple"])  # Output: 2.5
     ```
2. **Function Implementation**:
   - `total_cost_shopping`: Compute total cost from `price_list` and `quantity_list`.
   - `cost_of_fruit`: Calculate cost based on fruit type and quantity.
3. **Testing**:
   - Use PyTest to create test cases:
     ```python
     def test_cost_of_fruit():
         assert cost_of_fruit("apple", 2) == 5.0
     ```

#### **Exercise 5: Lists of Dictionaries**
1. **Database-like Usage**:
   - Example:
     ```python
     customers = [
         {"name": "Alice", "email": "alice@example.com"},
         {"name": "Bob", "email": "bob@example.com"}
     ]
     print(customers[0]["email"])  # Output: alice@example.com
     ```
2. **Function Implementation**:
   - Develop list-based operations for searching and updating data.
3. **Testing**:
   - Write comprehensive PyTest cases to validate dictionary manipulations.

---

## README Formatting Tips

1. **Markdown Syntax**:
   - Use headings (`#`, `##`, `###`) for structure.
   - Include code blocks with triple backticks (```) for clarity.
   - Add tables for structured information:
     | BMI Range        | Classification   |
     |------------------|------------------|
     | < 18.5           | Underweight      |
     | 18.5 - 25        | Normal Weight    |
     | > 25             | Overweight       |

2. **Embedding Images and Links**:
   - Use Markdown syntax for links and images:
     ```markdown
     ![Git Logo](https://git-scm.com/images/logo@2x.png)
     [Git Documentation](https://git-scm.com/doc)
     ```

3. **Ordered and Unordered Lists**:
   - Ordered:
     1. First step.
     2. Second step.
   - Unordered:
     - Item 1
     - Item 2

4. **Emphasize Text**:
   - Use `*italics*`, `**bold**`, or `~~strikethrough~~`.

---

## Key Notes and Resources

- **Useful Links**:
  - [Python Documentation](https://www.python.org)
  - [Git Documentation](https://git-scm.com)
  - [PyTest Documentation](https://pytest.org)
  - [Markdown Guide](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
- **Important Focus**:
  - Practice Exercises 4 and 5 from Lab 3 extensively.
  - Pay attention to creating comprehensive PyTest cases for advanced Python functions.
