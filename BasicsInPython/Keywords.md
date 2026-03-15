# [Keywords](#Keywords)


## 1. Topic Overview

**Keywords** in Python are **reserved words that have special meanings in the language**.

These words are part of Python’s **syntax and grammar**, and they **cannot be used as identifiers** (names for variables, functions, classes, etc.).

Example keywords:

```python
if
else
for
while
class
def
return
import
True
False
None
```

Example usage:

```python
if x > 10:
    print("Greater")
```

Here:

* `if` is a **keyword**
* It defines a **conditional statement**

So the key idea:

> **Keywords are reserved words that define Python’s syntax and structure.**

---

## 2. Problem it Solves

Programming languages need **fixed words to represent operations and control structures**.

Without keywords, it would be impossible for Python to understand program structure.

Example problem:

Imagine writing condition logic without predefined words.

```python
??? x > 10:
    print("Greater")
```

Python would not understand what to do.

Keywords solve this by defining:

| Purpose           | Keywords                            |
| ----------------- | ----------------------------------- |
| Conditional logic | `if`, `else`, `elif`                |
| Loops             | `for`, `while`                      |
| Functions         | `def`, `return`                     |
| Classes           | `class`                             |
| Error handling    | `try`, `except`, `finally`          |
| Boolean logic     | `True`, `False`, `and`, `or`, `not` |

Example:

```python
for i in range(5):
    print(i)
```

Here:

* `for`
* `in`

are **keywords controlling loop behavior**.

---

## 3. Concept Explanation

Python keywords are **predefined words with special meaning in the interpreter**.

They are used to build:

* control flow
* function definitions
* class definitions
* exception handling
* logical operations

Keywords **cannot be used as identifiers**.

Invalid example:

```python
class = 10
```

Output:

```
SyntaxError
```

Because `class` is a reserved keyword.

---

### Python Keywords List

Python currently has **35 keywords (Python 3.x)**.

```python
False
None
True
and
as
assert
async
await
break
class
continue
def
del
elif
else
except
finally
for
from
global
if
import
in
is
lambda
nonlocal
not
or
pass
raise
return
try
while
with
yield
```

You can view them using Python.

---

## 4. Internal Working

Internally, Python’s **parser recognizes keywords as tokens** during code parsing.

When Python reads code, it performs **lexical analysis**.

Example code:

```python
if x > 5:
    print(x)
```

Python tokenizes it like:

```
KEYWORD: if
IDENTIFIER: x
OPERATOR: >
NUMBER: 5
SYMBOL: :
IDENTIFIER: print
```

So keywords are recognized as **special tokens in Python grammar**.

---

### Token Types

Python interpreter categorizes tokens as:

| Token Type  | Example         |
| ----------- | --------------- |
| Keywords    | `if`, `for`     |
| Identifiers | `x`, `total`    |
| Operators   | `+`, `-`, `*`   |
| Literals    | `10`, `"hello"` |
| Delimiters  | `:`, `()`, `[]` |

Keywords belong to **reserved token types**.

---

## 5. Syntax

Keywords appear naturally in Python syntax.

Example syntax forms:

#### Conditional

```python
if condition:
    statement
```

#### Loop

```python
for variable in sequence:
    statement
```

#### Function

```python
def function_name():
    statements
```

#### Class

```python
class ClassName:
    statements
```

---

## 6. Code Examples

---

## Example 1 — Using `if` Keyword

```python
x = 10

if x > 5:
    print("x is greater than 5")
```

#### Output

```
x is greater than 5
```

Keyword used:

```
if
```

---

## Example 2 — Using `for` Keyword

```python
for i in range(3):
    print(i)
```

#### Output

```
0
1
2
```

Keywords used:

```
for
in
```

---

## Example 3 — Function with `def` and `return`

```python
def add(a, b):
    return a + b

print(add(3, 4))
```

#### Output

```
7
```

Keywords used:

```
def
return
```

---

## Example 4 — Using `class`

```python
class Student:
    pass

s = Student()
print(type(s))
```

#### Output

```
<class '__main__.Student'>
```

Keywords used:

```
class
pass
```

---

## Example 5 — Exception Handling

```python
try:
    x = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero")
```

#### Output

```
Cannot divide by zero
```

Keywords used:

```
try
except
```

---

## 7. Edge Cases

---

### 1. Using keywords as variable names

Invalid:

```python
for = 5
```

Error:

```
SyntaxError
```

Correct:

```python
for_value = 5
```

---

### 2. Using keywords inside identifiers

This is allowed.

```python
before = 10
format = "hello"
classroom = "A"
```

Even though they contain keyword text, they are valid identifiers.

---

### 3. Keywords vs Built-in Functions

Some words **look like keywords but are not**.

Example:

```
print
len
input
```

These are **built-in functions**, not keywords.

So this is valid:

```python
print = 10
```

But **not recommended** because it overrides built-in behavior.

---

## 8. Performance Considerations

Keywords themselves **do not affect runtime performance**, but they influence **program structure and execution flow**.

Example:

Efficient loop:

```python
for i in range(1000):
    pass
```

Here `for` keyword controls iteration.

---

### Bytecode Generation

When Python compiles code:

```python
if x > 5:
    print(x)
```

It generates **bytecode instructions** like:

```
COMPARE_OP
POP_JUMP_IF_FALSE
```

The keyword `if` determines **which bytecode instructions are produced**.

---

## 9. Common Mistakes

---

### Mistake 1 — Using keyword as variable

```python
return = 10
```

Error:

```
SyntaxError
```

---

### Mistake 2 — Confusing keywords with functions

Wrong assumption:

```
print is keyword ❌
```

Correct:

```
print is built-in function
```

---

### Mistake 3 — Not knowing Python keyword list

Developers sometimes accidentally use:

```python
async = 5
```

But `async` is a keyword.

---

## 10. Real World Usage

Keywords form the **core building blocks of Python programs**.

Example from real applications:

```python
def authenticate(user):
    if user.is_admin:
        return True
    else:
        return False
```

Keywords used:

```
def
if
return
else
```

Every Python program heavily depends on keywords.

---

## 11. Interview Questions

#### Basic

1. What are keywords in Python?
2. Can keywords be used as variable names?
3. Are keywords case-sensitive?

---

#### Intermediate

4. How many keywords exist in Python?
5. How can you get the list of Python keywords?
6. What is the difference between keyword and identifier?

---

#### Advanced

7. How does Python recognize keywords internally?
8. What are soft keywords in Python?
9. What happens if a keyword is used as a variable name?

---

## 12. Getting Keywords in Python

Python provides a module called `keyword`.

Example:

```python
import keyword

print(keyword.kwlist)
```

#### Output

```
['False', 'None', 'True', 'and', 'as', 'assert', ...]
```

To check if something is a keyword:

```python
import keyword

print(keyword.iskeyword("for"))
print(keyword.iskeyword("hello"))
```

Output:

```
True
False
```

---

## 13. Summary

Key points about **Python Keywords**:

* Keywords are **reserved words in Python**.
* They define **syntax and structure of programs**.
* **Cannot be used as identifiers**.
* Python has **35 keywords**.
* Examples: `if`, `for`, `class`, `def`, `return`, `try`.
* Python interpreter recognizes them during **lexical analysis and parsing**.
* Keywords help implement **loops, conditions, functions, and error handling**.

Example recap:

```python
def check_number(x):
    if x > 0:
        return "Positive"
    else:
        return "Negative"
```

Keywords used here:

```
def
if
return
else
```

---

