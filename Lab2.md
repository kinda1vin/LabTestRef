# ET0735 - DevOps for AIoT

## Laboratory 2: Introduction to Python

### Objectives

By the end of this lab, you will:

- Learn and implement Python programs focusing on:
  - Logical and mathematical operators
  - String processing
  - Data processing
- Practice creating Python functions for modularity and reusability.
- Use Git to manage and push projects to GitHub.
- Prepare solutions for lab tests with easily referable examples.

---

## Activities

### Installation and Setup
1. **Python Installation**:
   - Download [Python 3.11+](https://www.python.org/downloads/).
   - Install with:
     - **Tick**: Add Python to PATH
     - **Tick**: Disable path length limit.

2. **Visual Studio Code**:
   - Download [VS Code](https://code.visualstudio.com/).
   - Install and add Python extensions from the marketplace.
   - Configure Python 3.11 as the interpreter.

---

## Solutions for Lab Exercises

### Exercise 1: BMI Calculation
1. **Function Code** (`bmi.py`):
   ```python
   def calculate_bmi(height, weight):
       print("Height = " + str(height))
       print("Weight = " + str(weight))
       bmi = weight / (height ** 2)
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

   **Usage**:
   - Call `calculate_bmi()` with weight in kilograms and height in meters.
   - Outputs the BMI value and weight classification.

---

### Exercise 2: Console Application for Temperature Analysis
1. **Main Script** (`lab2.py`):
   ```python
   def display_main_menu():
       print("Enter some numbers separated by commas (e.g. 5, 67, 32)")

   def get_user_input():
       user_input = input()
       str_values = user_input.split(",")
       float_values = [float(value.strip()) for value in str_values]
       return float_values

   def calc_average(temps):
       return sum(temps) / len(temps) if temps else 0.0

   def find_min_max(temps):
       return [int(min(temps)), int(max(temps))] if temps else [0, 0]

   def sort_temperature(temps):
       return sorted(temps) if temps else []

   def calc_median_temperature(temps):
       sorted_temps = sort_temperature(temps)
       n = len(sorted_temps)
       return (sorted_temps[n//2 - 1] + sorted_temps[n//2]) / 2 if n % 2 == 0 else sorted_temps[n//2]

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

2. **Expected Usage**:
   - Run `main()` to input temperatures and compute:
     - Average temperature.
     - Min and max temperatures.
     - Median temperature.

---

### Exercise 3: Unit Testing with Pytest
1. **Test Cases** (`Test_Lab2.py`):
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

2. **Running Tests**:
   - Use `pytest` to run test cases:
     ```bash
     pytest Test_Lab2.py
     ```

---

## Git Tagging and Releases

1. **Tagging**:
   ```bash
   git tag -a Lab2_v1.0 -m "First release of Lab 2 solutions"
   git push origin Lab2_v1.0
   ```

2. **Creating a Release**:
   - Create a release on GitHub based on `Lab2_v1.0`.

---

## Markdown Tips for Lab Test

### Referencing Functions
- Use **code blocks** for clarity:
  ```python
  def calc_average(temps):
      return sum(temps) / len(temps)
  ```

### Test Outputs
- Include expected outputs as **comments** in code:
  ```python
  # Expected output:
  # Average temperature: 36.857142857142854
  ```

---

### Additional Resources
- [Python Input](https://www.w3schools.com/python/ref_func_input.asp)
- [Python Lists](https://www.w3schools.com/python/python_lists.asp)

This file is structured for quick referencing during lab tests or reviews. Feel free to modify it for personal clarity! 🎉