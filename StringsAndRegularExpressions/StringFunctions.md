# [String Functions](#String-Functions)

## 1. Topic Overview

**String functions** are built-in methods provided by Python that allow us to **manipulate, analyze, and transform strings**.

These functions help perform operations such as:

* converting case
* searching text
* replacing characters
* splitting strings
* removing spaces
* checking patterns

Example:

```python
text = "python programming"

print(text.upper())
```

Output:

```
PYTHON PROGRAMMING
```

So in simple words:

> **String functions are methods used to perform operations on string objects.**

---

## 2. Problem it Solves

Without string functions, processing text would be extremely difficult.

Example tasks solved by string functions:

| Problem                   | Function    |
| ------------------------- | ----------- |
| Convert text to uppercase | `upper()`   |
| Remove extra spaces       | `strip()`   |
| Split sentence into words | `split()`   |
| Find text in sentence     | `find()`    |
| Replace characters        | `replace()` |

Example:

```python
text = "  Hello World  "

print(text.strip())
```

Output:

```
Hello World
```

---

## 3. Concept Explanation

String functions are **methods attached to string objects**.

Syntax:

```
string.method(arguments)
```

Example:

```python
text = "python"

print(text.upper())
```

Here:

* `text` → string object
* `upper()` → method applied to the object

Important property:

> **Most string functions return a new string because strings are immutable.**

Example:

```python
text = "hello"
text.upper()

print(text)
```

Output:

```
hello
```

The original string does not change.

---

## 4. Internal Working

Python strings are **immutable Unicode sequences**.

When you call a string method:

```python
text.upper()
```

Python:

1. Reads the original string
2. Creates a new string object
3. Applies transformation
4. Returns the new string

Memory representation:

```
Original: "hello"

text.upper()

New object: "HELLO"
```

The original string stays unchanged.

---

## 5. Syntax

General syntax:

```python
string.method(parameters)
```

Example:

```python
text = "hello world"

text.upper()
text.split()
text.replace("hello", "hi")
```

---

## 6. Important String Functions

---

## `upper()`

Converts string to uppercase.

```python
text = "python"

print(text.upper())
```

Output

```
PYTHON
```

---

## `lower()`

Converts string to lowercase.

```python
text = "PYTHON"

print(text.lower())
```

Output

```
python
```

---

## `title()`

Capitalizes first letter of each word.

```python
text = "python programming language"

print(text.title())
```

Output

```
Python Programming Language
```

---

## `capitalize()`

Capitalizes first letter of entire string.

```python
text = "python programming"

print(text.capitalize())
```

Output

```
Python programming
```

---

## `strip()`

Removes whitespace from both sides.

```python
text = "   hello   "

print(text.strip())
```

Output

```
hello
```

---

#### `lstrip()`

Remove spaces from left.

```python
text = "   hello"

print(text.lstrip())
```

Output

```
hello
```

---

#### `rstrip()`

Remove spaces from right.

```python
text = "hello   "

print(text.rstrip())
```

Output

```
hello
```

---

## `replace()`

Replaces characters or substrings.

```python
text = "I like Java"

print(text.replace("Java","Python"))
```

Output

```
I like Python
```

---

## `split()`

Splits string into list.

```python
text = "apple banana mango"

print(text.split())
```

Output

```
['apple', 'banana', 'mango']
```

---

#### Split by delimiter

```python
text = "apple,banana,mango"

print(text.split(","))
```

Output

```
['apple', 'banana', 'mango']
```

---

## `join()`

Joins elements of a list into a string.

```python
words = ["Python","is","fun"]

print(" ".join(words))
```

Output

```
Python is fun
```

---

## `find()`

Finds position of substring.

```python
text = "Python programming"

print(text.find("program"))
```

Output

```
7
```

Returns **-1 if not found**.

---

## `startswith()`

Checks if string starts with given value.

```python
text = "Python programming"

print(text.startswith("Python"))
```

Output

```
True
```

---

## `endswith()`

Checks if string ends with value.

```python
text = "data.csv"

print(text.endswith(".csv"))
```

Output

```
True
```

---

## `count()`

Counts occurrences.

```python
text = "banana"

print(text.count("a"))
```

Output

```
3
```

---

## 7. Edge Cases

#### `find()` vs `index()`

`find()` returns `-1` if not found.

```python
text = "hello"

print(text.find("x"))
```

Output

```
-1
```

But `index()` raises error.

```python
text.index("x")
```

Error:

```
ValueError
```

---

#### Empty split

```python
text = ""

print(text.split())
```

Output

```
[]
```

---

## 8. Performance Considerations

Because strings are immutable, operations create **new objects**.

Example inefficient code:

```python
text = ""

for word in words:
    text += word
```

Better approach:

```python
text = " ".join(words)
```

`join()` is faster because it avoids repeated string allocation.

---

## 9. Common Mistakes

#### Mistake 1

Expecting methods to modify original string.

```python
text = "hello"
text.upper()

print(text)
```

Output:

```
hello
```

Correct:

```python
text = text.upper()
```

---

#### Mistake 2

Confusing `split()` and `join()`.

```
split() → string → list
join() → list → string
```

---

#### Mistake 3

Using `replace()` incorrectly.

```python
text.replace("a","b")
```

Returns new string.

---

## 10. Real World Usage

Example: processing CSV data.

```python
data = "John,25,Engineer"

fields = data.split(",")

print(fields)
```

Output

```
['John', '25', 'Engineer']
```

Example: cleaning input.

```python
name = "   Alice   "

clean_name = name.strip()

print(clean_name)
```

Output

```
Alice
```

---

## 11. Interview Questions

Basic:

1. What are string methods?
2. Difference between `upper()` and `capitalize()`?

Intermediate:

3. Difference between `split()` and `join()`?
4. What does `strip()` do?

Advanced:

5. Why are string operations slower in loops?
6. Explain immutability of strings.

---

## 12. Summary

String functions allow manipulation of text.

Important functions:

```
upper()
lower()
strip()
replace()
split()
join()
find()
startswith()
endswith()
count()
```

Example recap:

```python
text = " python programming "

print(text.strip().upper())
```

Output

```
PYTHON PROGRAMMING
```

---

