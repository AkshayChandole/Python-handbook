# [Built-in Functions and Modules](#Built-In-Functions-And-Modules)


## 1. Topic Overview

In Python, **Built-in Functions** and **Modules** provide ready-to-use functionality that allows programmers to perform common tasks without writing code from scratch.

#### Built-in Functions

These are **functions already available in Python** that you can use directly without importing anything.

Example:

```python
print("Hello")
len("Python")
type(10)
```

#### Modules

A **module** is a file that contains **Python code such as functions, classes, and variables** that can be reused in programs.

Example:

```python
import math
print(math.sqrt(16))
```

Output:

```
4.0
```

So in simple words:

> **Built-in functions are ready-made operations, and modules are collections of reusable code.**

---

## 2. Problem it Solves

Without built-in functions and modules, programmers would need to **write basic functionality repeatedly**.

Example problem:

To print output without `print()` you would need to manually implement output handling.

To compute square roots without `math` module you would need to write your own algorithm.

Built-in tools solve problems such as:

| Task                    | Tool            |
| ----------------------- | --------------- |
| Printing output         | `print()`       |
| Getting input           | `input()`       |
| Finding length          | `len()`         |
| Mathematical operations | `math` module   |
| Random numbers          | `random` module |
| System interaction      | `sys` module    |

These tools make programming **faster, simpler, and standardized**.

---

## 3. Concept Explanation

Python includes **many built-in functions and modules**.

#### Built-in Functions

Functions automatically available in Python.

Examples:

```text
print()
len()
type()
int()
float()
str()
sum()
max()
min()
range()
```

#### Modules

Modules contain **groups of related functions and classes**.

Examples:

| Module     | Purpose                      |
| ---------- | ---------------------------- |
| `math`     | Mathematical functions       |
| `random`   | Random number generation     |
| `sys`      | System-specific functions    |
| `os`       | Operating system interaction |
| `datetime` | Date and time operations     |

---

## 4. Internal Working

Internally, Python stores built-in functions in the **built-in namespace**.

Python searches identifiers using the **LEGB rule**:

```
Local
Enclosing
Global
Built-in
```

Example:

```python
print("Hello")
```

Python searches for `print`:

1. Local scope
2. Global scope
3. Built-in namespace

Finally finds:

```
builtins.print
```

Modules work differently.

When Python executes:

```python
import math
```

Python:

1. Searches for module in memory
2. Searches installed libraries
3. Loads module file
4. Creates module object

Then functions are accessed like:

```
math.function()
```

---

## 5. Syntax

#### Built-in Function Syntax

```
function_name(arguments)
```

Example:

```python
print("Hello")
len("Python")
```

---

#### Module Syntax

Importing modules:

```
import module_name
```

Example:

```python
import math
```

Using module functions:

```
module_name.function_name()
```

Example:

```python
math.sqrt(25)
```

---

## 6. Common Built-in Functions

---

### `print()`

Displays output.

```python
print("Hello World")
```

Output:

```
Hello World
```

---

### `len()`

Returns length of a sequence.

```python
text = "Python"
print(len(text))
```

Output:

```
6
```

---

### `type()`

Returns data type.

```python
x = 10
print(type(x))
```

Output:

```
<class 'int'>
```

---

### `input()`

Takes user input.

```python
name = input("Enter your name: ")
print(name)
```

Output (example):

```
Enter your name: John
John
```

---

### `sum()`

Calculates sum of elements.

```python
numbers = [1,2,3,4]
print(sum(numbers))
```

Output:

```
10
```

---

### `max()` and `min()`

Find maximum and minimum values.

```python
numbers = [5,2,9,1]

print(max(numbers))
print(min(numbers))
```

Output:

```
9
1
```

---

## 7. Important Built-in Modules

---

## Math Module

Provides mathematical functions.

Example:

```python
import math

print(math.sqrt(16))
print(math.factorial(5))
```

Output:

```
4.0
120
```

Some functions:

| Function      | Description |
| ------------- | ----------- |
| `sqrt()`      | Square root |
| `ceil()`      | Round up    |
| `floor()`     | Round down  |
| `factorial()` | Factorial   |

---

## Random Module

Generates random numbers.

Example:

```python
import random

print(random.randint(1,10))
```

Output (example):

```
7
```

Functions:

| Function    | Purpose        |
| ----------- | -------------- |
| `randint()` | Random integer |
| `random()`  | Random float   |
| `choice()`  | Random element |

---

## Datetime Module

Used for date and time operations.

Example:

```python
import datetime

now = datetime.datetime.now()

print(now)
```

Output example:

```
2026-03-15 12:30:45
```

---

## Sys Module

Provides system information.

Example:

```python
import sys

print(sys.version)
```

Output example:

```
3.11.4
```

---

## 8. Edge Cases

#### Overriding built-in functions

You can accidentally overwrite built-ins.

```python
print = 10
print("Hello")
```

Error occurs because `print` is no longer a function.

---

#### Import alias

Modules can be imported with shorter names.

```python
import math as m

print(m.sqrt(25))
```

Output:

```
5.0
```

---

#### Import specific functions

```python
from math import sqrt

print(sqrt(36))
```

Output:

```
6.0
```

---

## 9. Performance Considerations

Using built-in functions is usually **faster than writing custom implementations** because they are written in **optimized C code**.

Example:

Fast:

```python
sum(numbers)
```

Slower:

```python
total = 0
for n in numbers:
    total += n
```

Modules also avoid code duplication and improve **performance and maintainability**.

---

## 10. Common Mistakes

#### Mistake 1

Forgetting to import module.

```python
math.sqrt(16)
```

Error:

```
NameError
```

Correct:

```python
import math
math.sqrt(16)
```

---

#### Mistake 2

Confusing built-in functions and module functions.

Example:

```
len() → built-in
sqrt() → math module
```

---

#### Mistake 3

Overwriting built-ins.

```python
list = [1,2,3]
```

Avoid using names like:

```
list
str
int
sum
```

---

## 11. Real World Usage

Example program using multiple built-ins and modules:

```python
import math
import random

numbers = [4,9,16,25]

print("Length:", len(numbers))
print("Max:", max(numbers))

random_number = random.randint(1,10)

print("Random:", random_number)

print("Square root of 16:", math.sqrt(16))
```

Output example:

```
Length: 4
Max: 25
Random: 6
Square root of 16: 4.0
```

Built-in functions and modules are used in:

* data analysis
* web development
* machine learning
* automation
* scientific computing

---

## 12. Interview Questions

#### Basic

1. What are built-in functions in Python?
2. What is a module?
3. What is the difference between built-in functions and modules?

#### Intermediate

4. How do you import a module?
5. What is the difference between `import` and `from ... import`?
6. What is aliasing in Python modules?

#### Advanced

7. Explain Python namespaces.
8. How does Python locate modules during import?
9. What is the difference between built-in modules and user-defined modules?

---

## 13. Summary

Key points:

* **Built-in functions** are ready-to-use functions available in Python.
* **Modules** are files containing reusable Python code.
* Built-in functions examples:

```
print()
len()
type()
sum()
max()
min()
input()
```

* Important modules include:

```
math
random
datetime
sys
os
```

Example recap:

```python
import math

numbers = [1,2,3]

print(len(numbers))
print(math.sqrt(25))
```

Output:

```
3
5.0
```

Built-in functions and modules make Python **powerful, efficient, and easy to use**.

---

If you'd like, I can also explain **Python Standard Library (50+ most useful modules every developer should know)** — which is a **very important topic for exams and interviews**.

