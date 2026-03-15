
# [Introduction to Strings](#Introduction-to-Strings)



## 1. Topic Overview

A **string** in Python is a **sequence of characters** used to represent text.

Characters can include:

* letters (`a-z`, `A-Z`)
* digits (`0-9`)
* symbols (`@ ## $ %`)
* whitespace

Examples:

```python
name = "Alice"
message = "Hello World"
password = "abc@123"
```

In Python:

> A string is an **immutable sequence of Unicode characters**.

This means:

* Characters are stored in order.
* Strings cannot be changed after creation.

---

## 2. Problem it Solves

Strings allow programs to work with **textual data**, which is essential in real-world applications.

Examples:

| Use Case        | Example                  |
| --------------- | ------------------------ |
| User names      | `"John"`                 |
| Email addresses | `"user@email.com"`       |
| File paths      | `"C:/data/file.txt"`     |
| API responses   | `"status: success"`      |
| Logs            | `"Error: invalid input"` |

Without strings, software could not process **text data**, which is a huge part of computing.

---

## 3. Concept Explanation

A string is simply a **collection of characters enclosed in quotes**.

Python supports multiple ways to create strings.

#### Single Quotes

```python
text = 'Python'
```

#### Double Quotes

```python
text = "Python"
```

Both are identical.

---

#### Triple Quotes (Multiline Strings)

Used for large blocks of text.

```python
text = """Python is
a powerful
programming language"""
```

Output:

```
Python is
a powerful
programming language
```

---

## 4. Internal Working

In Python, **strings are objects**.

Example:

```python
text = "Python"
```

Internally Python stores:

```
Object Type: str
Value: Python
```

Memory representation:

```
text
  |
  v
+---+---+---+---+---+---+
| P | y | t | h | o | n |
+---+---+---+---+---+---+
 0   1   2   3   4   5
```

Each character has an **index**.

---

### Unicode Support

Python strings use **Unicode encoding**, meaning they support characters from many languages.

Example:

```python
text = "こんにちは"
print(text)
```

Output:

```
こんにちは
```

---

## 5. Syntax

General syntax:

```python
string_variable = "text"
```

Examples:

```python
name = "Alice"
city = 'London'
message = "Hello World"
```

---

## 6. Code Examples

---

### Example 1: Basic String

```python
text = "Python"

print(text)
```

Output:

```
Python
```

---

### Example 2: String with Quotes

```python
text = "It's a sunny day"
print(text)
```

Output:

```
It's a sunny day
```

---

### Example 3: Multiline String

```python
message = """Hello
Welcome to
Python"""

print(message)
```

Output:

```
Hello
Welcome to
Python
```

---

## 7. String Indexing

Each character in a string has a **position (index)**.

Example:

```python
text = "Python"

print(text[0])
print(text[3])
```

Output:

```
P
h
```

Index positions:

```
P  y  t  h  o  n
0  1  2  3  4  5
```

---

### Negative Indexing

Python allows accessing characters from the end.

```
P  y  t  h  o  n
-6 -5 -4 -3 -2 -1
```

Example:

```python
text = "Python"

print(text[-1])
```

Output:

```
n
```

---

## 8. String Slicing

Slicing extracts part of a string.

Syntax:

```
string[start:end]
```

Example:

```python
text = "Python"

print(text[0:3])
```

Output:

```
Pyt
```

Explanation:

```
Start = 0
End = 3 (excluded)
```

---

#### Step slicing

```python
text = "Python"

print(text[::2])
```

Output:

```
Pto
```

---

## 9. Immutability of Strings

Strings cannot be modified after creation.

Example:

```python
text = "Python"
text[0] = "J"
```

Output:

```
TypeError
```

Instead you create a **new string**.

```python
text = "Python"

new_text = "J" + text[1:]
print(new_text)
```

Output:

```
Jython
```

---

## 10. Edge Cases

#### Empty string

```python
text = ""
```

Length is zero.

---

#### Escape characters

Used for special formatting.

Examples:

| Escape | Meaning   |
| ------ | --------- |
| `\n`   | New line  |
| `\t`   | Tab       |
| `\\`   | Backslash |

Example:

```python
print("Hello\nWorld")
```

Output:

```
Hello
World
```

---

## 11. Performance Considerations

Strings are **immutable**, so operations like concatenation create new objects.

Example:

```python
text = "Hello"
text = text + " World"
```

Python creates a **new string object**.

For large concatenations, use:

```python
" ".join(list_of_strings)
```

Which is more memory efficient.

---

## 12. Common Mistakes

#### Mistake 1: Forgetting quotes

```python
text = Python
```

Error:

```
NameError
```

---

#### Mistake 2: Confusing indexing

```python
text = "Python"
print(text[6])
```

Error:

```
IndexError
```

Because valid indexes are `0–5`.

---

#### Mistake 3: Modifying strings

```python
text[0] = "J"
```

Not allowed due to immutability.

---

## 13. Real World Usage

Strings are used in almost every Python program.

Example: simple greeting program.

```python
name = input("Enter your name: ")

message = "Hello " + name

print(message)
```

Output example:

```
Enter your name: Alice
Hello Alice
```

Strings are used in:

* web development
* APIs
* file processing
* data analysis
* automation scripts

---

## 14. Interview Questions

Basic:

1. What is a string in Python?
2. Are Python strings mutable or immutable?
3. What is string indexing?

Intermediate:

4. Difference between slicing and indexing?
5. What are escape characters?

Advanced:

6. How are Python strings stored internally?
7. Why is string concatenation slow in loops?

---

## 15. Summary

Key points:

* Strings represent **text data**.
* They are **immutable sequences of characters**.
* Created using quotes:

```
'string'
"string"
"""multiline string"""
```

Important operations:

```
Indexing
Slicing
Concatenation
Length calculation
```

Example recap:

```python
text = "Python"

print(text[0])
print(text[1:4])
```

Output:

```
P
yth
```

---
