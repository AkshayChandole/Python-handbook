# [Data Type Conversions](#DataTypeConversions)


## 1. Topic Overview

**Data Type Conversion** in Python is the process of **changing a value from one data type to another**.

In simple terms:

> **Data type conversion means converting one type of data into another type.**

Example:

```python
x = "10"
y = int(x)

print(y)
print(type(y))
```

Output:

```
10
<class 'int'>
```

Here:

* `"10"` → string
* `10` → integer

So the data type **changed from string to integer**.

Python supports **two types of conversions**:

1. **Implicit Type Conversion**
2. **Explicit Type Conversion (Type Casting)**

---

## 2. Problem it Solves

Different data types behave differently. Sometimes we must convert them to perform operations.

Example problem:

```python
x = "10"
y = 5

print(x + y)
```

Output:

```
TypeError
```

Because Python **cannot add string and integer**.

Solution:

```python
x = int("10")
y = 5

print(x + y)
```

Output:

```
15
```

Data type conversion ensures **compatible operations between data types**.

---

## 3. Concept Explanation

Python automatically or manually converts data types.

Two main categories:

| Conversion Type     | Description                   |
| ------------------- | ----------------------------- |
| Implicit Conversion | Python converts automatically |
| Explicit Conversion | Programmer converts manually  |

---

## 4. Internal Working

Internally, Python stores every value as an **object with a type**.

Example:

```python
x = 10
```

Internally:

```
x → object
     type = int
     value = 10
```

When conversion occurs:

```python
float(x)
```

Python **creates a new object**:

```
x → 10 (int)
float(x) → 10.0 (float)
```

The original object **remains unchanged**.

---

## 5. Implicit Type Conversion

Implicit conversion is also called **automatic conversion**.

Python automatically converts a smaller data type to a larger one.

Example hierarchy:

```
int → float → complex
```

---

#### Example 1

```python
x = 5
y = 2.5

result = x + y

print(result)
print(type(result))
```

Output:

```
7.5
<class 'float'>
```

Explanation:

* `5` is `int`
* `2.5` is `float`

Python automatically converts:

```
5 → 5.0
```

Then performs addition.

---

#### Example 2

```python
a = 3
b = 2 + 4j

result = a + b

print(result)
print(type(result))
```

Output:

```
(5+4j)
<class 'complex'>
```

Conversion:

```
int → complex
```

---

## 6. Explicit Type Conversion (Type Casting)

Explicit conversion is done **manually by the programmer** using built-in functions.

Example:

```python
int()
float()
str()
list()
tuple()
set()
dict()
bool()
```

---

### Integer Conversion

```python
x = "25"

y = int(x)

print(y)
print(type(y))
```

Output:

```
25
<class 'int'>
```

---

### Float Conversion

```python
x = 10

y = float(x)

print(y)
```

Output:

```
10.0
```

---

### String Conversion

```python
x = 100

y = str(x)

print(y)
print(type(y))
```

Output:

```
100
<class 'str'>
```

---

### List Conversion

```python
text = "Python"

result = list(text)

print(result)
```

Output:

```
['P', 'y', 't', 'h', 'o', 'n']
```

---

### Tuple Conversion

```python
numbers = [1,2,3]

t = tuple(numbers)

print(t)
```

Output:

```
(1, 2, 3)
```

---

### Set Conversion

```python
numbers = [1,2,2,3]

s = set(numbers)

print(s)
```

Output:

```
{1, 2, 3}
```

Duplicate values are removed.

---

### Boolean Conversion

Python converts values to `True` or `False`.

Example:

```python
print(bool(1))
print(bool(0))
```

Output:

```
True
False
```

Rules:

```
0 → False
None → False
Empty structures → False
Everything else → True
```

Example:

```python
print(bool(""))
print(bool("Hello"))
```

Output:

```
False
True
```

---

## 7. Edge Cases

#### Invalid Conversion

```python
int("hello")
```

Output:

```
ValueError
```

Because `"hello"` cannot be converted to an integer.

---

#### Float to Integer

```python
x = 5.9
print(int(x))
```

Output:

```
5
```

Decimal part is **truncated**, not rounded.

---

#### String to List

```python
list("ABC")
```

Output:

```
['A','B','C']
```

---

#### Dictionary Conversion

```python
pairs = [("a",1),("b",2)]

d = dict(pairs)

print(d)
```

Output:

```
{'a':1,'b':2}
```

---

## 8. Performance Considerations

Conversions require **creating new objects in memory**.

Example:

```python
x = "100"
y = int(x)
```

Python:

1. Reads string object `"100"`
2. Creates new integer object `100`

Frequent conversions can impact performance in **large loops**.

Example inefficient code:

```python
for i in range(1000000):
    int("10")
```

Better approach:

```python
value = int("10")

for i in range(1000000):
    result = value + i
```

---

## 9. Common Mistakes

#### Mistake 1 — Mixing incompatible types

```python
"10" + 5
```

Error:

```
TypeError
```

Correct:

```python
int("10") + 5
```

---

#### Mistake 2 — Converting invalid strings

```python
int("12a")
```

Error:

```
ValueError
```

---

#### Mistake 3 — Expecting rounding

```python
int(9.9)
```

Output:

```
9
```

Not `10`.

---

## 10. Real World Usage

Example: user input conversion.

```python
age = input("Enter your age: ")

age = int(age)

print(age + 5)
```

Because `input()` always returns a **string**, conversion is necessary.

---

Example: data processing.

```python
price = "100"
tax_rate = 0.18

total = int(price) * (1 + tax_rate)

print(total)
```

Conversions are very common in:

* data processing
* APIs
* databases
* user input

---

## 11. Interview Questions

Basic:

1. What is type conversion in Python?
2. Difference between implicit and explicit conversion?
3. What does `int()` do?

Intermediate:

4. What happens when converting float to int?
5. How does Python handle automatic conversion?

Advanced:

6. Why does Python convert `int` to `float` automatically?
7. What happens internally during type casting?
8. How does Python store objects during conversion?

---

## 12. Summary

Key points about **Data Type Conversion**:

* Conversion changes a **value from one data type to another**.
* Python supports **two types of conversion**.

#### 1. Implicit Conversion

Automatic conversion by Python.

Example:

```
int + float → float
```

#### 2. Explicit Conversion

Manual conversion using functions:

```
int()
float()
str()
list()
tuple()
set()
dict()
bool()
```

Example recap:

```python
x = "10"
y = int(x)

print(y + 5)
```

Output:

```
15
```

Data type conversion helps **ensure compatibility between different types of data**.

---
