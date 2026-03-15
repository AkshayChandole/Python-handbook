
# [Conversion and Comparison of Strings](#Conversion-and-Comparison-of-Strings)


## 1. Topic Overview

**Conversion and Comparison of Strings** involve two important operations:

1. **Conversion** – Changing strings into other data types or converting other data types into strings.
2. **Comparison** – Comparing two strings to determine if they are equal, greater, or smaller.

These operations are extremely important when working with:

* user input
* file data
* APIs
* text processing
* validation

Example:

```python
a = "10"
b = 20

print(int(a) + b)
```

Output

```
30
```

Here the string `"10"` is **converted to an integer**.

---

## 2. Problem it Solves

Many times data arrives as **text**, even if it represents numbers.

Example:

```python
age = input("Enter age: ")
```

The `input()` function always returns a **string**.

If we try:

```python
print(age + 5)
```

Error occurs.

Solution:

```python
age = int(age)
print(age + 5)
```

Similarly, comparing strings helps with tasks like:

* password checking
* sorting names
* filtering text
* validating inputs

---

## 3. Concept Explanation

Two main topics here:

#### 1. String Conversion

Changing a string into another data type or vice versa.

#### 2. String Comparison

Checking if strings are:

* equal
* greater
* smaller

Python compares strings using **lexicographical ordering** (dictionary order).

Example:

```
"apple" < "banana"
```

Result:

```
True
```

Because `"a"` comes before `"b"`.

---

## 4. Internal Working

Python compares strings using **Unicode values** of characters.

Example:

```
'A' → 65
'B' → 66
'a' → 97
```

So when comparing:

```
"apple" < "banana"
```

Python compares:

```
'a' vs 'b'
97 vs 98
```

Since `97 < 98`, the result is **True**.

Python compares **character by character**.

Example:

```
"car" vs "cat"
```

Comparison process:

```
c = c
a = a
r < t
```

So `"car" < "cat"` is **True**.

---

## 5. Syntax

#### Conversion

```python
int(string)
float(string)
str(number)
```

#### Comparison

```python
string1 == string2
string1 != string2
string1 > string2
string1 < string2
string1 >= string2
string1 <= string2
```

---

## 6. String Conversion

---

## Convert String → Integer

```python
text = "100"

num = int(text)

print(num)
print(type(num))
```

Output

```
100
<class 'int'>
```

---

## Convert String → Float

```python
price = "19.99"

value = float(price)

print(value)
```

Output

```
19.99
```

---

## Convert Number → String

```python
num = 25

text = str(num)

print(text)
print(type(text))
```

Output

```
25
<class 'str'>
```

---

## Convert String → List

```python
text = "Python"

letters = list(text)

print(letters)
```

Output

```
['P', 'y', 't', 'h', 'o', 'n']
```

---

## Convert List → String

```python
words = ["Python", "is", "fun"]

sentence = " ".join(words)

print(sentence)
```

Output

```
Python is fun
```

---

## 7. String Comparison

String comparison uses comparison operators.

| Operator | Meaning          |
| -------- | ---------------- |
| `==`     | equal            |
| `!=`     | not equal        |
| `>`      | greater          |
| `<`      | smaller          |
| `>=`     | greater or equal |
| `<=`     | smaller or equal |

---

## Equality Comparison

```python
a = "apple"
b = "apple"

print(a == b)
```

Output

```
True
```

---

## Lexicographical Comparison

```python
print("apple" < "banana")
```

Output

```
True
```

---

## Character Comparison

```python
print("cat" > "car")
```

Output

```
True
```

Explanation:

```
t > r
```

---

## Case Sensitivity

String comparisons are **case-sensitive**.

```python
print("apple" == "Apple")
```

Output

```
False
```

Because:

```
'A' != 'a'
```

---

## Case-Insensitive Comparison

Use `lower()` or `upper()`.

```python
a = "Python"
b = "python"

print(a.lower() == b.lower())
```

Output

```
True
```

---

## 8. Edge Cases

#### Invalid Conversion

```python
int("abc")
```

Error:

```
ValueError
```

Because `"abc"` cannot be converted to an integer.

---

#### Numeric Strings vs Numbers

```python
print("10" > "2")
```

Output

```
False
```

Explanation:

```
"1" < "2"
```

So `"10"` is considered smaller.

---

#### Comparing different types

```python
"10" > 5
```

Error:

```
TypeError
```

Python cannot compare string with integer.

---

## 9. Performance Considerations

String comparison is efficient because Python:

* compares characters sequentially
* stops as soon as difference is found

Example:

```
"apple" vs "zebra"
```

Python compares only first character.

Complexity:

```
O(n)
```

Where **n = string length**.

---

## 10. Common Mistakes

#### Mistake 1

Comparing numeric strings incorrectly.

```python
print("100" > "20")
```

Output:

```
False
```

Correct approach:

```python
print(int("100") > int("20"))
```

---

#### Mistake 2

Forgetting case sensitivity.

```python
print("Hello" == "hello")
```

False.

---

#### Mistake 3

Converting invalid strings.

```python
int("12a")
```

Raises error.

---

## 11. Real World Usage

#### User login validation

```python
username = input("Enter username: ")

if username.lower() == "admin":
    print("Welcome admin")
```

---

#### Sorting names

```python
names = ["Alice", "Bob", "Charlie"]

print(sorted(names))
```

Output

```
['Alice', 'Bob', 'Charlie']
```

Sorting uses **string comparison rules**.

---

#### Data parsing

```python
price = "100"

total = int(price) * 2

print(total)
```

Output

```
200
```

---

## 12. Interview Questions

Basic

1. How do you convert string to integer in Python?
2. What is lexicographical comparison?

Intermediate

3. Why is `"10" < "2"` true in string comparison?
4. How can you perform case-insensitive comparison?

Advanced

5. How does Python compare strings internally?
6. What is Unicode-based comparison?

---

## 13. Summary

#### String Conversion

Used to change types.

Common conversions:

```
int()
float()
str()
list()
join()
```

Example:

```python
num = int("10")
```

---

#### String Comparison

Strings are compared **lexicographically using Unicode values**.

Example:

```python
print("apple" < "banana")
```

Output

```
True
```

---

Example recap:

```python
a = "Python"
b = "python"

print(a.lower() == b.lower())
```

Output

```
True
```

---
