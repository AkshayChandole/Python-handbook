# [Regular Expressions](#Regular-Expressions)

## 1. Topic Overview

**Regular Expressions (Regex)** are patterns used to **search, match, and manipulate text**.

They allow you to define **rules for matching sequences of characters**.

Example:

Suppose we want to find all **emails** in a text.

Regex pattern:

```
\w+@\w+\.\w+
```

Python example:

```python
import re

text = "Contact us at support@email.com"

result = re.search(r"\w+@\w+\.\w+", text)

print(result.group())
```

Output:

```
support@email.com
```

So in simple terms:

> **Regular Expressions are powerful patterns used for text searching and pattern matching.**

---

## 2. Problem it Solves

Regex is extremely useful for **text processing tasks**.

Without regex, searching text becomes complicated.

Example tasks:

| Problem                   | Regex Use        |
| ------------------------- | ---------------- |
| Extract email addresses   | pattern matching |
| Validate phone numbers    | input validation |
| Extract numbers from text | data parsing     |
| Log analysis              | pattern search   |
| Password validation       | rule checking    |

Example:

```python
import re

text = "My number is 9876543210"

numbers = re.findall(r"\d+", text)

print(numbers)
```

Output:

```
['9876543210']
```

Regex helps automate **complex text processing**.

---

## 3. Concept Explanation

A **regular expression** is a **pattern that describes a set of strings**.

Example patterns:

| Pattern | Meaning          |
| ------- | ---------------- |
| `a`     | match letter "a" |
| `abc`   | match "abc"      |
| `\d`    | digit            |
| `\w`    | word character   |
| `.`     | any character    |

Example:

```python
import re

text = "cat bat rat"

result = re.findall(r"at", text)

print(result)
```

Output:

```
['at', 'at', 'at']
```

---

## 4. Internal Working

Regex works using a **pattern matching engine**.

Steps:

1. Python reads regex pattern
2. Compiles it internally
3. Scans the target string
4. Matches characters according to pattern rules

Example:

```
Pattern: cat
Text:    cat dog cat
```

Regex engine checks sequentially:

```
c a t → match
d o g → no match
c a t → match
```

Result:

```
["cat", "cat"]
```

Python uses a **backtracking regex engine**.

---

## 5. Regex Module in Python

Python provides regex functionality through the **`re` module**.

Import:

```python
import re
```

Important functions:

| Function       | Description        |
| -------------- | ------------------ |
| `re.search()`  | search first match |
| `re.match()`   | match at start     |
| `re.findall()` | find all matches   |
| `re.sub()`     | replace matches    |
| `re.split()`   | split by pattern   |

---

## 6. Basic Regex Syntax

#### Literal characters

Match exact characters.

Example:

```python
import re

text = "cat dog cat"

print(re.findall("cat", text))
```

Output

```
['cat', 'cat']
```

---

#### Special Characters

| Symbol | Meaning         |
| ------ | --------------- |
| `.`    | any character   |
| `^`    | start of string |
| `$`    | end of string   |
| `*`    | zero or more    |
| `+`    | one or more     |
| `?`    | optional        |

Example:

```python
re.findall("c.t", "cat cot cut")
```

Output:

```
['cat', 'cot', 'cut']
```

---

## 7. Important Regex Patterns

#### Digits

```
\d
```

Matches numbers.

Example:

```python
import re

text = "Order 1234"

print(re.findall(r"\d+", text))
```

Output:

```
['1234']
```

---

#### Word characters

```
\w
```

Matches:

```
letters
digits
underscore
```

Example:

```python
re.findall(r"\w+", "Hello World")
```

Output:

```
['Hello', 'World']
```

---

#### Whitespace

```
\s
```

Matches spaces, tabs, newlines.

Example:

```python
re.findall(r"\s", "Hello World")
```

Output:

```
[' ']
```

---

## 8. Code Examples

---

## Example 1: Find numbers

```python
import re

text = "My score is 95 and 88"

numbers = re.findall(r"\d+", text)

print(numbers)
```

Output

```
['95', '88']
```

---

## Example 2: Find words

```python
import re

text = "Python is awesome"

words = re.findall(r"\w+", text)

print(words)
```

Output

```
['Python', 'is', 'awesome']
```

---

## Example 3: Replace text

```python
import re

text = "I love Java"

new_text = re.sub("Java", "Python", text)

print(new_text)
```

Output

```
I love Python
```

---

## Example 4: Split text

```python
import re

text = "apple,banana;orange"

result = re.split("[,;]", text)

print(result)
```

Output

```
['apple', 'banana', 'orange']
```

---

## 9. Edge Cases

#### Raw Strings

Regex patterns often use **raw strings (`r""`)**.

Example:

```python
r"\n"
```

Without raw string:

```
"\n"
```

Python interprets it as newline.

Raw strings prevent escape issues.

---

#### Greedy matching

Example:

```python
re.findall("a.*b", "a123b456b")
```

Output:

```
['a123b456b']
```

Regex captures the **longest match**.

---

## 10. Performance Considerations

Regex can be computationally expensive.

Example inefficient:

```python
re.search(pattern, text)
```

in a loop.

Better approach:

```python
pattern = re.compile(r"\d+")

pattern.findall(text)
```

Compiled regex improves performance.

---

## 11. Common Mistakes

#### Forgetting raw string

Wrong:

```python
"\d+"
```

Correct:

```python
r"\d+"
```

---

#### Confusing match and search

```
match() → start only
search() → anywhere
```

Example:

```python
re.match("cat","dog cat")
```

No match.

---

#### Using wrong pattern

Example:

```
\d → one digit
\d+ → many digits
```

---

## 12. Real World Usage

Regex is heavily used in:

* web scraping
* data cleaning
* log analysis
* form validation
* cybersecurity
* NLP

Example: email extraction

```python
import re

text = "Contact: admin@test.com"

emails = re.findall(r"\w+@\w+\.\w+", text)

print(emails)
```

Output

```
['admin@test.com']
```

---

## 13. Interview Questions

Basic:

1. What is a regular expression?
2. What is the `re` module?

Intermediate:

3. Difference between `search()` and `match()`?
4. What does `\d+` mean?

Advanced:

5. What is greedy matching?
6. How does regex backtracking work?

---

## 14. Summary

Regular expressions allow **powerful text pattern matching**.

Important components:

Patterns:

```
\d → digit
\w → word character
\s → whitespace
.  → any character
```

Functions:

```
re.search()
re.match()
re.findall()
re.sub()
re.split()
```

Example recap:

```python
import re

text = "Price: 100"

print(re.findall(r"\d+", text))
```

Output:

```
['100']
```

---
