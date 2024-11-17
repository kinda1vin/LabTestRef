
# Python Cheat Sheet for ET0735 Labs

## General Python Basics

### Variables and Data Types
- **Assigning Variables**:
  ```python
  x = 10      # Integer
  y = 3.14    # Float
  name = "John"  # String
  is_valid = True  # Boolean
  print(x, y, name, is_valid)
  ```
  **Output**:  
  `10 3.14 John True`

- **Type Conversion**:
  ```python
  print(int("123"))       # Convert string to integer
  print(float("12.34"))   # Convert string to float
  print(str(123))         # Convert number to string
  ```
  **Output**:  
  `123`  
  `12.34`  
  `'123'`

### Arithmetic Operators
- **Addition**: `+`  
  ```python
  print(5 + 3)
  ```
  **Output**:  
  `8`  

- **Subtraction**: `-`  
  ```python
  print(5 - 3)
  ```
  **Output**:  
  `2`

- **Multiplication**: `*`  
  ```python
  print(5 * 3)
  ```
  **Output**:  
  `15`

- **Division**: `/`  
  ```python
  print(5 / 2)
  ```
  **Output**:  
  `2.5`

- **Integer Division**: `//`  
  ```python
  print(5 // 2)
  ```
  **Output**:  
  `2`

- **Modulo (Remainder)**: `%`  
  ```python
  print(5 % 2)
  ```
  **Output**:  
  `1`

- **Exponentiation**: `**`  
  ```python
  print(2 ** 3)
  ```
  **Output**:  
  `8`

### Logical and Comparison Operators
- **Logical Operators**:
  ```python
  print(True and False)
  print(True or False)
  print(not True)
  ```
  **Output**:  
  `False`  
  `True`  
  `False`  

- **Comparison Operators**:
  ```python
  print(5 == 5)
  print(5 != 3)
  print(5 > 3)
  print(5 < 10)
  print(5 >= 5)
  print(5 <= 10)
  ```
  **Output**:  
  `True`  
  `True`  
  `True`  
  `True`  
  `True`  
  `True`  

---

## Built-in Python Functions

### Commonly Used Functions
- **`print()`**: Displays output to the console.
  ```python
  print("Hello, World!")
  ```
  **Output**:  
  `Hello, World!`

- **`len()`**: Returns the length of an object.
  ```python
  print(len("Hello"))
  ```
  **Output**:  
  `5`

- **`type()`**: Returns the type of an object.
  ```python
  print(type(123))
  ```
  **Output**:  
  `<class 'int'>`

- **`sum()`**: Sums up a list of numbers.
  ```python
  numbers = [1, 2, 3]
  print(sum(numbers))
  ```
  **Output**:  
  `6`

- **`max()` / `min()`**: Finds the maximum or minimum value in a list.
  ```python
  print(max([1, 2, 3]))
  print(min([1, 2, 3]))
  ```
  **Output**:  
  `3`  
  `1`  

- **`sorted()`**: Returns a sorted list.
  ```python
  print(sorted([3, 1, 2]))
  ```
  **Output**:  
  `[1, 2, 3]`

- **`zip()`**: Combines two or more iterables element-wise into tuples.
  ```python
  list1 = [1, 2, 3]
  list2 = ['a', 'b', 'c']
  print(list(zip(list1, list2)))
  ```
  **Output**:  
  `[(1, 'a'), (2, 'b'), (3, 'c')]`

- **`enumerate()`**: Adds an index to an iterable.
  ```python
  items = ['apple', 'banana', 'cherry']
  for index, item in enumerate(items):
      print(index, item)
  ```
  **Output**:  
  `0 apple`  
  `1 banana`  
  `2 cherry`  

---

## File Handling
- **Opening and Reading a File**:
  ```python
  with open("file.txt", "w") as file:
      file.write("Hello, World!")
  with open("file.txt", "r") as file:
      print(file.read())
  ```
  **Output**:  
  `Hello, World!`

---

## PyTest Basics
- **Writing Tests**:
  ```python
  def add(a, b):
      return a + b

  def test_add():
      assert add(2, 3) == 5
  ```

- **Running Tests**:
  ```bash
  pytest <test_file>.py
  ```

---

## Additional Notes
- Always test edge cases for better code reliability.
- Use `dir(object)` to explore available methods and attributes.

---

---

## Additional Useful Built-in Functions

### Numeric Functions
- **`abs()`**: Returns the absolute value of a number.
  ```python
  print(abs(-10))
  ```
  **Output**:  
  `10`

- **`round()`**: Rounds a number to the nearest integer or specified decimal places.
  ```python
  print(round(3.14159, 2))
  ```
  **Output**:  
  `3.14`

- **`pow()`**: Returns the power of a number (equivalent to `x ** y`).
  ```python
  print(pow(2, 3))
  ```
  **Output**:  
  `8`

### Iterable Operations
- **`all()`**: Returns `True` if all elements in an iterable are `True`.
  ```python
  print(all([True, True, False]))
  ```
  **Output**:  
  `False`

- **`any()`**: Returns `True` if at least one element in an iterable is `True`.
  ```python
  print(any([False, True, False]))
  ```
  **Output**:  
  `True`

- **`reversed()`**: Returns an iterator that accesses the given sequence in reverse order.
  ```python
  print(list(reversed([1, 2, 3])))
  ```
  **Output**:  
  `[3, 2, 1]`

- **`filter()`**: Filters elements of an iterable based on a function.
  ```python
  numbers = [1, 2, 3, 4, 5]
  even_numbers = filter(lambda x: x % 2 == 0, numbers)
  print(list(even_numbers))
  ```
  **Output**:  
  `[2, 4]`

- **`map()`**: Applies a function to all elements in an iterable.
  ```python
  numbers = [1, 2, 3, 4]
  squares = map(lambda x: x ** 2, numbers)
  print(list(squares))
  ```
  **Output**:  
  `[1, 4, 9, 16]`

### String Operations
- **`str.join()`**: Joins elements of an iterable into a string.
  ```python
  print(", ".join(["apple", "banana", "cherry"]))
  ```
  **Output**:  
  `apple, banana, cherry`

- **`str.split()`**: Splits a string into a list.
  ```python
  print("apple,banana,cherry".split(","))
  ```
  **Output**:  
  `['apple', 'banana', 'cherry']`

- **`str.replace()`**: Replaces occurrences of a substring.
  ```python
  print("Hello World".replace("World", "Python"))
  ```
  **Output**:  
  `Hello Python`

### Type Conversion Functions
- **`list()`**: Converts an iterable into a list.
  ```python
  print(list("abc"))
  ```
  **Output**:  
  `['a', 'b', 'c']`

- **`set()`**: Converts an iterable into a set (unique elements).
  ```python
  print(set([1, 2, 2, 3]))
  ```
  **Output**:  
  `{1, 2, 3}`

- **`dict()`**: Converts a list of key-value pairs into a dictionary.
  ```python
  pairs = [("key1", "value1"), ("key2", "value2")]
  print(dict(pairs))
  ```
  **Output**:  
  `{'key1': 'value1', 'key2': 'value2'}`

- **`tuple()`**: Converts an iterable into a tuple.
  ```python
  print(tuple([1, 2, 3]))
  ```
  **Output**:  
  `(1, 2, 3)`

---

### Debugging and Exploration
- **`help()`**: Displays the documentation for a function or module.
  ```python
  help(len)
  ```
  **Output**:  
  Displays the documentation for `len`.

- **`dir()`**: Lists the attributes and methods of an object.
  ```python
  print(dir([]))
  ```
  **Output**:  
  Displays all methods available for a list.

- **`id()`**: Returns the memory address of an object.
  ```python
  print(id(123))
  ```
  **Output**:  
  Memory address of the object.

---

## Best Practices
- Use `help()` and `dir()` to explore unfamiliar functions.
- Chain functions like `map()` and `filter()` for efficient data processing.

---
