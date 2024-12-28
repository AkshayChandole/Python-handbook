# [**Python Basics**](#python-basics)

Python is a versatile and beginner-friendly language known for its simplicity, readability, and extensive standard library. Mastering the basics is crucial for building a strong foundation in Python programming. Below, we'll explore essential concepts like **Data Types**, **Variables**, **Operators**, **Conditionals**, and **Loops**, with detailed explanations and examples.

---

## [**1. Data Types**](#1-data-types)
Data types define the kind of value a variable can hold. Python has several built-in data types.

### **Core Data Types:**
1. **Numeric Types**: `int`, `float`, `complex`
   - `int`: Integer values (e.g., `42`)
   - `float`: Decimal values (e.g., `3.14`)
   - `complex`: Complex numbers (e.g., `3 + 4j`)

2. **Sequence Types**: `str`, `list`, `tuple`
   - `str`: Text data (e.g., `"hello"`)
   - `list`: Ordered, mutable collection (e.g., `[1, 2, 3]`)
   - `tuple`: Ordered, immutable collection (e.g., `(1, 2, 3)`)

3. **Mapping Type**: `dict`
   - Stores key-value pairs (e.g., `{"name": "Alice", "age": 25}`)

4. **Set Types**: `set`, `frozenset`
   - `set`: Unordered collection of unique items (e.g., `{1, 2, 3}`)
   - `frozenset`: Immutable version of a set.

5. **Boolean Type**: `bool`
   - Represents `True` or `False`.

6. **NoneType**: `None`
   - Represents the absence of a value.

### **Example:**
```python
x = 42                 # int
y = 3.14               # float
z = 3 + 4j             # complex
text = "Hello World"   # str
items = [1, 2, 3]      # list
person = {"name": "Alice", "age": 25}  # dict
unique_items = {1, 2, 3}  # set
flag = True            # bool
nothing = None         # NoneType
```

### **Checking Data Types:**
Use the `type()` function.
```python
print(type(x))  # <class 'int'>
```

---

## [**2. Variables**](#2-variables)
Variables store data in memory. They are dynamically typed in Python, meaning you don’t need to declare their type.

### **Rules for Naming Variables:**
- Must begin with a letter or an underscore (`_`).
- Can contain letters, numbers, and underscores.
- Case-sensitive (`myVar` and `myvar` are different).

### **Example:**
```python
age = 25
name = "Alice"
is_student = True
```

---

## [**3. Operators**](#3-operators)
Operators perform operations on variables and values. Python supports several types of operators:

### **Arithmetic Operators:**
```python
a = 10
b = 3
print(a + b)  # Addition: 13
print(a - b)  # Subtraction: 7
print(a * b)  # Multiplication: 30
print(a / b)  # Division: 3.333...
print(a // b) # Floor Division: 3
print(a % b)  # Modulus: 1
print(a ** b) # Exponentiation: 1000
```

### **Comparison Operators:**
```python
print(a == b)  # Equal to: False
print(a != b)  # Not equal to: True
print(a > b)   # Greater than: True
```

### **Logical Operators:**
```python
print(True and False)  # Logical AND: False
print(True or False)   # Logical OR: True
print(not True)        # Logical NOT: False
```

---

## [**4. Conditionals**](#4-conditionals)
Conditionals control the flow of code based on conditions using `if`, `elif`, and `else`.

### **Example:**
```python
x = 15

if x > 10:
    print("x is greater than 10")
elif x == 10:
    print("x is equal to 10")
else:
    print("x is less than 10")
```

### **Output:**
```
x is greater than 10
```

---

## [**5. Loops**](#5-loops)
Loops execute a block of code multiple times.

### **Types of Loops:**
1. **`for` Loop:**
   Iterates over a sequence.
   ```python
   for i in range(5):
       print(i)
   ```
   **Output:**
   ```
   0
   1
   2
   3
   4
   ```

2. **`while` Loop:**
   Executes as long as the condition is `True`.
   ```python
   count = 0
   while count < 5:
       print(count)
       count += 1
   ```
   **Output:**
   ```
   0
   1
   2
   3
   4
   ```

### **Breaking out of Loops:**
- **`break`**: Exit the loop.
- **`continue`**: Skip the current iteration.

### **Example:**
```python
for i in range(5):
    if i == 3:
        break
    print(i)
```
**Output:**
```
0
1
2
```
---
