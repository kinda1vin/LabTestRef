# ET0735 - DevOps for AIoT

## Laboratory 2: Introduction to Python

---

## Objectives

By the end of this lab, you will:
- Understand basic Python programming concepts.
- Learn to implement Python functions for modular and reusable code.
- Perform data processing with string manipulations, lists, and mathematical operations.
- Manage and push Python projects using Git and GitHub.
- Test Python code using `pytest`.

---

## Setting Up

### Installation
1. **Python Installation**:
   - Download Python 3.11+ from [python.org](https://www.python.org/downloads/).
   - Install with:
     - **Tick**: Add Python to PATH.
     - **Tick**: Disable path length limit.

2. **Visual Studio Code**:
   - Download [VS Code](https://code.visualstudio.com/).
   - Install and add the Python extension from the Extensions Marketplace.
   - Configure Python 3.11 as the interpreter.

---

## Solutions for Lab Exercises

### **Exercise 1: BMI Calculation**

#### Code Implementation
1. **`bmi.py`**:
   ```python
   def calculate_bmi(height, weight):
       print("Height = " + str(height))
       print("Weight = " + str(weight))
       bmi = weight / (height ** 2)  # BMI formula: weight(kg) / height(m)^2
       print("BMI = " + str(bmi))

       if bmi < 18.5:
           print("Underweight")
           return -1
       elif bmi < 25:
           print("Normal Weight")
           return 0
       else:
           print("Overweight")
           return 1

   returnValue = calculate_bmi(weight=57, height=1.73)
   print(returnValue)
   ```

#### Explanation:
- **Function Purpose**: Calculate BMI and classify weight.
- **Formula**: \( BMI = \frac{weight}{height^2} \).
- **Classification**:
  - \( BMI < 18.5 \): Underweight.
  - \( 18.5 \leq BMI < 25 \): Normal weight.
  - \( BMI \geq 25 \): Overweight.
- **Return Values**:
  - `-1`: Underweight.
  - `0`: Normal weight.
  - `1`: Overweight.

#### Extra Notes:
- The function uses **type casting** (`str()`) to ensure compatibility between strings and numbers when printing.
- Always validate user inputs for height and weight in real-world applications to avoid division by zero or invalid data types.

---

### **Exercise 2: Temperature Analysis Console Application**

#### Code Implementation
1. **`lab2.py`**:
   ```python
   def display_main_menu():
       print("Enter some numbers separated by commas (e.g. 5, 67, 32)")

   def get_user_input():
       user_input = input()
       str_values = user_input.split(",")  # Split input by commas
       float_values = [float(value.strip()) for value in str_values]  # Convert strings to floats
       return float_values

   def calc_average(temps):
       return sum(temps) / len(temps) if temps else 0.0  # Avoid division by zero

   def find_min_max(temps):
       return [min(temps), max(temps)] if temps else [0, 0]  # Handle empty lists

   def sort_temperature(temps):
       return sorted(temps) if temps else []  # Return sorted list

   def calc_median_temperature(temps):
       sorted_temps = sort_temperature(temps)
       n = len(sorted_temps)
       if n % 2 == 0:
           return (sorted_temps[n//2 - 1] + sorted_temps[n//2]) / 2  # Median for even count
       return sorted_temps[n//2]  # Median for odd count

   def main():
       print("ET0735 (DevOps for AIoT) - Lab 2 - Introduction to Python")
       display_main_menu()
       num_list = get_user_input()

       print(f"Average temperature: {calc_average(num_list)}")
       print(f"Min and Max temperatures: {find_min_max(num_list)}")
       print(f"Median temperature: {calc_median_temperature(num_list)}")

   if __name__ == "__main__":
       main()
   ```

#### Explanation:
- **Functions**:
  - **`display_main_menu()`**: Provides user instructions.
  - **`get_user_input()`**:
    - Reads input as a comma-separated string.
    - Splits and converts values into a list of floats.
  - **`calc_average(temps)`**: Computes the average temperature.
  - **`find_min_max(temps)`**: Finds the minimum and maximum temperatures.
  - **`sort_temperature(temps)`**: Returns a sorted list.
  - **`calc_median_temperature(temps)`**: Computes the median.
- **Main Function**:
  - Organizes the execution of the program by calling functions in sequence.

#### Extra Notes:
- **Input Validation**:
  - Ensure non-numeric values are handled gracefully with `try-except`.
  - Example:
    ```python
    try:
        float_values = [float(value.strip()) for value in str_values]
    except ValueError:
        print("Invalid input. Please enter only numbers.")
    ```
- **Median Calculation**:
  - Handles both even and odd number counts in the list.

---

### **Exercise 3: Unit Testing**

#### Code Implementation
1. **`Test_Lab2.py`**:
   ```python
   import lab2

   def test_min_max():
       input_arr = [64, 34, 25, 12, 22, 11, 90]
       assert lab2.find_min_max(input_arr) == [11, 90]

   def test_average():
       input_arr = [64, 34, 25, 12, 22, 11, 90]
       assert lab2.calc_average(input_arr) == 36.857142857142854

   def test_median_temperature():
       input_arr = [64, 34, 25, 12, 22, 11, 90]
       assert lab2.calc_median_temperature(input_arr) == 25
   ```

#### Explanation:
- **Purpose**:
  - Validate the correctness of implemented functions.
- **Structure**:
  - Each function is tested with sample input and expected output.
  - `pytest` checks if the actual output matches the expected output.

#### Running Tests:
- Command:
  ```bash
  pytest Test_Lab2.py
  ```
- Output:
  - Success or failure of each test case is reported.

#### Extra Notes:
- Add edge cases like empty lists, large numbers, or invalid input to ensure robustness.

---

## Git Workflow

### Commands:
1. Initialize repository:
   ```bash
   git init
   ```
2. Add files:
   ```bash
   git add *
   ```
3. Commit changes:
   ```bash
   git commit -m "Initial commit for Lab 2 solutions"
   ```
4. Push to GitHub:
   ```bash
   git remote add origin <GitHub_repository_URL>
   git push --set-upstream origin master
   ```

### Tagging and Releases:
1. Add a tag:
   ```bash
   git tag -a Lab2_v1.1 -m "Release v1.1"
   git push origin Lab2_v1.1
   ```
2. Create a release on GitHub using the tag.

---

## Additional Tips for Lab Tests

- Use **docstrings** to explain each function:
  ```python
  def calc_average(temps):
      """Calculate the average of a list of temperatures."""
      return sum(temps) / len(temps) if temps else 0.0
  ```
- Practice with edge cases and common errors like invalid input or empty lists.
- Always add comments for complex logic or formulas.

---

## References
- [Python Input](https://www.w3schools.com/python/ref_func_input.asp)
- [Python Lists](https://www.w3schools.com/python/python_lists.asp)

This file is designed to help you quickly reference and understand solutions during lab tests or reviews. Good luck! 🎉