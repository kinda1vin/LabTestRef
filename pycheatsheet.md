
# Python Cheat Sheet for ET0735 Labs

## General Python Basics

### Variables and Data Types
- **Assigning Variables**:
  ```python
  x = 10      # Integer
  y = 3.14    # Float
  name = "John"  # String
  is_valid = True  # Boolean
  ```

- **Type Conversion**:
  ```python
  int("123")       # Convert string to integer
  float("12.34")   # Convert string to float
  str(123)         # Convert number to string
  ```

### Arithmetic Operators
- **Addition**: `+`  
  Example: `result = 5 + 3  # result = 8`  
- **Subtraction**: `-`  
  Example: `result = 5 - 3  # result = 2`
- **Multiplication**: `*`  
  Example: `result = 5 * 3  # result = 15`
- **Division**: `/`  
  Example: `result = 5 / 2  # result = 2.5`
- **Integer Division**: `//`  
  Example: `result = 5 // 2  # result = 2`
- **Modulo (Remainder)**: `%`  
  Example: `result = 5 % 2  # result = 1`
- **Exponentiation**: `**`  
  Example: `result = 2 ** 3  # result = 8`

### Logical and Comparison Operators
- **Logical Operators**:
  - AND: `and`
  - OR: `or`
  - NOT: `not`
  ```python
  if x > 0 and y > 0:
      print("Both positive")
  ```

- **Comparison Operators**:
  - Equal: `==`
  - Not Equal: `!=`
  - Greater Than: `>`
  - Less Than: `<`
  - Greater or Equal: `>=`
  - Less or Equal: `<=`

---

## String Operations
- **Concatenation**: `+`
  ```python
  greeting = "Hello" + " " + "World"
  ```
- **Repetition**: `*`
  ```python
  repeated = "Hi! " * 3  # "Hi! Hi! Hi! "
  ```
- **String Methods**:
  - Length: `len()`
  - Convert to Upper: `.upper()`
  - Convert to Lower: `.lower()`
  - Strip Whitespaces: `.strip()`
  ```python
  name = "  John  "
  print(name.strip())  # "John"
  ```

---

## Lists
- **Creating a List**:
  ```python
  numbers = [1, 2, 3, 4, 5]
  ```
- **Accessing Elements**:
  ```python
  first = numbers[0]  # First element
  last = numbers[-1]  # Last element
  ```
- **List Operations**:
  - Add: `append()`
  - Remove: `remove()`
  - Sort: `sort()`
  ```python
  numbers.append(6)
  numbers.sort()
  ```

---

## Dictionaries
- **Creating a Dictionary**:
  ```python
  data = {"key1": "value1", "key2": "value2"}
  ```
- **Accessing Values**:
  ```python
  value = data["key1"]
  ```
- **Adding/Updating**:
  ```python
  data["key3"] = "value3"
  ```
- **Iterating**:
  ```python
  for key, value in data.items():
      print(key, value)
  ```

---

## Control Flow
- **If Statements**:
  ```python
  if x > 0:
      print("Positive")
  elif x == 0:
      print("Zero")
  else:
      print("Negative")
  ```
- **For Loops**:
  ```python
  for num in range(5):
      print(num)
  ```
- **While Loops**:
  ```python
  while x > 0:
      x -= 1
      print(x)
  ```

---

## Functions
- **Defining Functions**:
  ```python
  def add(a, b):
      return a + b
  ```
- **Calling Functions**:
  ```python
  result = add(5, 3)
  print(result)
  ```

---

## File Handling
- **Opening and Reading a File**:
  ```python
  with open("file.txt", "r") as file:
      content = file.read()
  ```
- **Writing to a File**:
  ```python
  with open("file.txt", "w") as file:
      file.write("Hello, World!")
  ```

---

## Error Handling
- **Try-Except Block**:
  ```python
  try:
      result = 10 / 0
  except ZeroDivisionError:
      print("Cannot divide by zero!")
  ```

---

## PyTest Basics
- **Writing Tests**:
  ```python
  def test_add():
      assert add(2, 3) == 5
  ```
- **Running Tests**:
  ```bash
  pytest <test_file>.py
  ```

---

## Useful Tips
- Use `help(function_name)` to view documentation for any Python function.
- Use `dir(object_name)` to list all methods and attributes of an object.
- Use `type(variable)` to check the type of a variable.
