# ET0735 - DevOps for AIoT

## Laboratory 3: Developing Software Unit Tests

---

## Objectives

By the end of this lab, you will:
- Understand the use of **PyTest** for software unit testing.
- Create and execute unit tests for Python functions.
- Implement Python programs with dictionaries and lists for database-like operations.
- Manage Git repositories with submodules.
- Ensure test-driven development by verifying code correctness through unit tests.

---

## Solutions for Lab 3 Exercises

---

### **Exercise 1: BMI Unit Testing**

#### Code Files:
1. **`bmi.py`**:
   Contains the implementation of BMI calculation:
   ```python
   def calculate_bmi(height, weight):
       bmi = weight / (height ** 2)
       if bmi < 18.5:
           return -1  # Underweight
       elif bmi < 25:
           return 0  # Normal weight
       else:
           return 1  # Overweight
   ```

2. **`Test_bmi.py`**:
   Implements PyTest unit tests for `calculate_bmi`:
   ```python
   def test_bmi_overweight():
       assert bmi.calculate_bmi(1.73, 90) == 1

   def test_bmi_normal_weight():
       assert bmi.calculate_bmi(1.73, 70) == 0

   def test_bmi_underweight():
       assert bmi.calculate_bmi(1.73, 50) == -1
   ```

#### Explanation:
- `test_bmi_overweight()`: Verifies the overweight classification.
- `test_bmi_normal_weight()`: Checks normal weight classification.
- `test_bmi_underweight()`: Validates underweight classification.

---

### **Exercise 2: Bubble Sort**

#### Code File:
1. **`Lab3.py`**:
   Contains a `bubble_sort` function to sort lists:
   ```python
   def bubble_sort(arr, sorting_order):
       if not all(isinstance(x, int) for x in arr):
           return 2  # Invalid input
       n = len(arr)
       if n == 0:
           return 0  # No elements
       elif n >= 10:
           return 1  # Too many elements
       else:
           for i in range(n - 1):
               for j in range(0, n - i - 1):
                   if sorting_order == SORT_ASCENDING and arr[j] > arr[j + 1]:
                       arr[j], arr[j + 1] = arr[j + 1], arr[j]
                   elif sorting_order == SORT_DESCENDING and arr[j] < arr[j + 1]:
                       arr[j], arr[j + 1] = arr[j + 1], arr[j]
           return arr
   ```

2. **`Test_Lab3.py`**:
   Implements tests for the `bubble_sort` function:
   ```python
   def test_bubble_sort_ascending():
       assert Lab3.bubble_sort([64, 34, 25], Lab3.SORT_ASCENDING) == [25, 34, 64]

   def test_bubble_sort_descending():
       assert Lab3.bubble_sort([64, 34, 25], Lab3.SORT_DESCENDING) == [64, 34, 25]

   def test_bubble_sort_invalid():
       assert Lab3.bubble_sort([64, "34", 25], Lab3.SORT_ASCENDING) == 2
   ```

---

### **Exercise 3: Employee Management**

#### Code File:
1. **`employee_info.py`**:
   Contains functions to manage employee data:
   ```python
   def calculate_average_salary():
       return sum(emp["salary"] for emp in employee_data) / len(employee_data)

   def get_employees_by_age_range(min_age, max_age):
       return [emp for emp in employee_data if min_age <= emp["age"] <= max_age]

   def get_employees_by_dept(department):
       return [emp for emp in employee_data if emp["department"] == department]
   ```

2. **`test_employee_info.py`**:
   Implements unit tests for employee functions:
   ```python
   def test_calculate_average_salary():
       assert employee_info.calculate_average_salary() == 60166.67

   def test_get_employees_by_age_range():
       assert employee_info.get_employees_by_age_range(30, 40) == [...]

   def test_get_employees_by_dept():
       assert employee_info.get_employees_by_dept("Sales") == [...]
   ```

---

### **Exercise 4: Price Information**

#### Code File:
1. **`price_info.py`**:
   Contains functions for calculating the cost of fruits:
   ```python
   def total_cost_shopping():
       total = sum(price_list[fruit] * quantity_list[fruit] for fruit in price_list)
       return total

   def cost_of_fruits(fruit, quantity):
       return price_list.get(fruit, 0) * quantity
   ```

2. **`test_price_info.py`**:
   Implements unit tests for price functions:
   ```python
   def test_total_cost_shopping():
       assert price_info.total_cost_shopping() == 46.75

   def test_cost_of_fruits():
       assert price_info.cost_of_fruits("apple", 10) == 12.0
   ```

---

## Git Workflow

### Steps:
1. Clone the repository:
   ```bash
   git clone <repository_url>
   ```
2. Add and commit changes:
   ```bash
   git add *
   git commit -m "Added Lab 3 solutions"
   ```
3. Push changes:
   ```bash
   git push origin main
   ```
4. Create a Git tag:
   ```bash
   git tag -a Lab3_v1.0 -m "First release"
   git push origin Lab3_v1.0
   ```

---

## Notes

### General Best Practices:
- Validate inputs in all functions to prevent runtime errors.
- Add meaningful comments to explain complex logic.
- Use PyTest's `assert` for comprehensive testing.

### Unit Testing Tips:
- Test edge cases, such as empty lists or invalid inputs.
- Ensure test cases are independent and do not rely on external state.

---

Feel free to use this document as a quick reference for implementing and testing Lab 3! 🎉