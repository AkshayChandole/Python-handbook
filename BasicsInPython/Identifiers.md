 # [Identifiers](#Identifiers)

## 1. Topic Overview

**Identifiers** are the names used to identify **variables, functions, classes, modules, and other objects** in Python.

In simple words:

> **An identifier is the name given to a programming element.**

Examples of identifiers:

```python
name = "Alice"
age = 25
calculate_total()
Student
```

Here:

* `name` → identifier for a variable
* `age` → identifier for a variable
* `calculate_total` → identifier for a function
* `Student` → identifier for a class

Identifiers allow programmers to **refer to data and program elements using meaningful names** instead of raw values.

---

# 2. Problem It Solves

Without identifiers, programming would be extremely difficult.

Imagine writing code like this:

```python
"John" = 25
```

There would be **no way to reference data later**.

Identifiers solve these problems:

| Problem              | Solution using Identifiers       |
| -------------------- | -------------------------------- |
| Storing data         | Variables like `age`, `name`     |
| Reusing logic        | Functions like `calculate_sum()` |
| Structuring programs | Classes like `Student`           |
| Accessing modules    | Names like `math`, `sys`         |

Example:

```python
price = 100
tax = 5
total = price + tax
```

Identifiers (`price`, `tax`, `total`) make code **readable and manageable**.

---

# 3. Concept Explanation

An **identifier** is simply a **name assigned to a programming element**.

Python uses identifiers for:

* Variables
* Functions
* Classes
* Modules
* Objects
* Packages

Example:

```python
x = 10
```

Here:

* `x` → identifier
* `10` → value

---

## Rules for Identifiers

Python has strict rules for naming identifiers.

### 1. Must start with a letter or underscore

Valid:

```python
name = "John"
_age = 25
```

Invalid:

```python
1name = "John"   # ❌
```

---

### 2. Can contain letters, digits, and underscores

Valid:

```python
student1 = "Alice"
total_sum = 100
```

Invalid:

```python
total-sum = 100   # ❌ hyphen not allowed
```

---

### 3. Cannot use Python keywords

Keywords are reserved words used by Python.

Example keywords:

```
if
else
for
while
class
def
return
```

Invalid:

```python
class = 10   # ❌ invalid
```

---

### 4. Identifiers are case-sensitive

Python treats uppercase and lowercase as different.

```python
age = 10
Age = 20
AGE = 30
```

These are **three different identifiers**.

---

### 5. Cannot contain spaces

Invalid:

```python
student name = "John"   # ❌
```

Correct:

```python
student_name = "John"
```

---

# 4. Internal Working

Internally, Python stores identifiers in **symbol tables**.

When Python executes code:

```python
x = 10
```

Python does the following:

Step 1: Create integer object `10` in memory.

Step 2: Create identifier `x`.

Step 3: Map identifier `x` → memory location of `10`.

Representation:

```
Identifier Table

x  →  10
```

Example:

```python
x = 10
y = x
```

Memory mapping:

```
x → 10
y → 10
```

Both identifiers refer to the **same object**.

---

# 5. Syntax

There is **no special syntax** for identifiers. They appear naturally in declarations.

General format:

```python
identifier = value
```

Examples:

```python
name = "Alice"
count = 10
total_sum = 50
```

Function identifiers:

```python
def calculate_area():
    pass
```

Class identifiers:

```python
class Student:
    pass
```

---

# 6. Code Examples

---

## Example 1 — Basic Identifier

```python
age = 25
print(age)
```

### Output

```
25
```

---

## Example 2 — Multiple Identifiers

```python
name = "Alice"
city = "London"
age = 30

print(name, city, age)
```

### Output

```
Alice London 30
```

---

## Example 3 — Identifier in Functions

```python
def greet():
    print("Hello")

greet()
```

### Output

```
Hello
```

Here:

* `greet` is an identifier for a function.

---

## Example 4 — Identifier in Classes

```python
class Student:
    pass

s = Student()
print(type(s))
```

### Output

```
<class '__main__.Student'>
```

---

## Example 5 — Case Sensitivity

```python
value = 10
Value = 20

print(value)
print(Value)
```

### Output

```
10
20
```

---

# 7. Edge Cases

### 1. Using underscore

Underscores are valid:

```python
_user = "admin"
```

Used commonly for:

* temporary variables
* internal variables

---

### 2. Single underscore `_`

Python often uses `_` as a throwaway variable.

Example:

```python
for _ in range(3):
    print("Hello")
```

Output:

```
Hello
Hello
Hello
```

---

### 3. Double underscore `__`

Often used in special methods:

```python
__init__
__str__
```

These are called **dunder methods (double underscore methods)**.

---

### 4. Unicode identifiers

Python even allows Unicode identifiers.

```python
π = 3.14
print(π)
```

Output:

```
3.14
```

Though **not recommended for production code**.

---

# 8. Performance Considerations

Identifiers themselves **do not significantly affect performance**, but good naming helps:

### 1. Readability

Bad:

```python
x1 = 10
x2 = 20
x3 = x1 + x2
```

Better:

```python
price = 10
tax = 20
total = price + tax
```

---

### 2. Namespace lookup

Python resolves identifiers through namespaces:

1. Local
2. Enclosing
3. Global
4. Built-in

This is called the **LEGB rule**.

Example:

```python
len([1,2,3])
```

Python looks up `len` in built-ins.

---

# 9. Common Mistakes

---

### Mistake 1 — Starting with number

```python
1value = 10
```

Error:

```
SyntaxError
```

Correct:

```python
value1 = 10
```

---

### Mistake 2 — Using keywords

```python
for = 10
```

Error:

```
SyntaxError
```

---

### Mistake 3 — Spaces in identifiers

```python
user name = "John"
```

Correct:

```python
user_name = "John"
```

---

### Mistake 4 — Confusing similar names

```python
l = 10
I = 20
O = 30
```

Hard to read.

Better:

```python
length = 10
index = 20
output = 30
```

---

# 10. Real World Usage

Identifiers are used everywhere in Python programs.

Example from real project:

```python
def calculate_total_price(price, tax_rate):
    tax = price * tax_rate
    total_price = price + tax
    return total_price
```

Identifiers used:

* `calculate_total_price`
* `price`
* `tax_rate`
* `tax`
* `total_price`

Good identifiers make **large codebases maintainable**.

---

# 11. Interview Questions

### Basic Questions

1. What is an identifier in Python?
2. What characters are allowed in identifiers?
3. Can identifiers start with numbers?
4. Are Python identifiers case-sensitive?

---

### Intermediate Questions

5. What happens if an identifier matches a keyword?
6. What is the LEGB rule?
7. Can Python identifiers contain Unicode characters?

---

### Advanced Questions

8. How does Python resolve identifiers internally?
9. What is the difference between identifiers and variables?
10. How are identifiers stored in Python symbol tables?

---

# 12. Summary

Key points about **Python Identifiers**:

* Identifiers are **names for variables, functions, classes, and objects**.
* Must start with **letter or underscore**.
* Can contain **letters, digits, and underscores**.
* **Cannot start with numbers**.
* **Cannot use Python keywords**.
* **Case-sensitive** (`age`, `Age`, `AGE` are different).
* Used to make code **readable and maintainable**.
* Python stores identifiers in **symbol tables and namespaces**.

Example recap:

```python
name = "Alice"
age = 25

def greet():
    print("Hello", name)
```

Identifiers here are:

```
name
age
greet
```

---

