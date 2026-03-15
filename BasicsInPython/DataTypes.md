# [Data Types](#Data-Types)

## 1. Topic Overview

A **Data Type** in Python defines the **type of value a variable can hold** and the **operations that can be performed on it**.

In simple terms:

> **Data types specify what kind of data a variable stores.**

Example:

```python
x = 10        ## Integer
name = "John" ## String
price = 10.5  ## Float
```

Each value has a **specific type**, and Python uses this type to determine how the value behaves.

Python is a **dynamically typed language**, meaning you do not need to declare a type explicitly.

Example:

```python
x = 10
x = "Hello"
```

The variable `x` changes type automatically.

---

## 2. Problem it Solves

Data types help Python understand:

* **How data should be stored**
* **What operations are allowed**
* **How memory should be allocated**

Example problem without data types:

```python
10 + "Hello"
```

Python cannot add a number and a string.

Error:

```
TypeError
```

Data types ensure that operations are **logically valid and predictable**.

---

## 3. Concept Explanation

Python provides **built-in data types** that are grouped into categories.

Main Python data types:

| Category | Data Types                   |
| -------- | ---------------------------- |
| Numeric  | int, float, complex          |
| Text     | str                          |
| Sequence | list, tuple, range           |
| Mapping  | dict                         |
| Set      | set, frozenset               |
| Boolean  | bool                         |
| Binary   | bytes, bytearray, memoryview |
| None     | NoneType                     |

Example:

```python
x = 10
print(type(x))
```

Output:

```
<class 'int'>
```

The `type()` function tells the **data type of a value**.

---

## 4. Internal Working

In Python, **everything is an object**.

Each object contains:

1. **Type**
2. **Value**
3. **Reference count**
4. **Memory address**

Example:

```python
x = 10
```

Internally:

```
x → object(10)
      type: int
      value: 10
```

If another variable refers to the same object:

```python
y = x
```

Memory mapping:

```
x → 10
y → 10
```

Both point to the **same object** in memory.

---

## 5. Numeric Data Types

Python numeric types represent numbers.

### Integer (int)

An **integer** represents whole numbers.

Example:

```python
x = 10
y = -5
z = 1000
```

Example code:

```python
x = 20
y = 5

print(x + y)
```

Output:

```
25
```

Integers in Python have **unlimited precision**.

Example:

```python
x = 999999999999999999999999999
print(x)
```

Python handles it automatically.

---

### Float

Float represents **decimal numbers**.

Example:

```python
price = 10.5
temperature = -3.7
```

Example:

```python
x = 5.5
y = 2.0

print(x / y)
```

Output:

```
2.75
```

Floats follow **IEEE 754 double precision format** internally.

---

### Complex

Complex numbers contain **real and imaginary parts**.

Format:

```
a + bj
```

Example:

```python
x = 2 + 3j
print(x)
```

Output:

```
(2+3j)
```

Access parts:

```python
x = 2 + 3j

print(x.real)
print(x.imag)
```

Output:

```
2.0
3.0
```

---

## 6. String Data Type

A **string** is a sequence of characters.

Example:

```python
name = "Alice"
city = 'London'
```

Python allows:

* Single quotes
* Double quotes
* Triple quotes

Example:

```python
text = """Python
Programming
Language"""
```

Example:

```python
name = "John"

print(name.upper())
```

Output:

```
JOHN
```

Strings are **immutable** (cannot be modified).

Example:

```python
name = "John"
name[0] = "A"
```

Error:

```
TypeError
```

---

## 7. Sequence Data Types

Sequence types store **multiple values in order**.

Types include:

* list
* tuple
* range

---

### List

A **list** is an ordered, mutable collection.

Example:

```python
numbers = [1, 2, 3, 4]
```

Example:

```python
numbers = [10, 20, 30]

print(numbers[1])
```

Output:

```
20
```

Lists allow modification:

```python
numbers[1] = 50
```

---

### Tuple

A **tuple** is an ordered but **immutable** collection.

Example:

```python
coordinates = (10, 20)
```

Example:

```python
point = (5, 6)

print(point[0])
```

Output:

```
5
```

Attempting modification causes error.

---

### Range

Range represents a sequence of numbers.

Example:

```python
range(5)
```

Example:

```python
for i in range(3):
    print(i)
```

Output:

```
0
1
2
```

---

## 8. Mapping Data Type

### Dictionary (dict)

A dictionary stores **key-value pairs**.

Example:

```python
student = {
    "name": "Alice",
    "age": 20
}
```

Example:

```python
student = {"name": "John", "age": 22}

print(student["name"])
```

Output:

```
John
```

Dictionaries are **mutable**.

---

## 9. Set Data Types

Sets store **unique elements**.

Types:

* set
* frozenset

---

### Set

Example:

```python
numbers = {1, 2, 3, 4}
```

Example:

```python
numbers = {1, 2, 2, 3}

print(numbers)
```

Output:

```
{1, 2, 3}
```

Duplicates are removed.

---

### FrozenSet

A **frozenset** is an immutable set.

Example:

```python
fs = frozenset([1,2,3])
```

Cannot modify after creation.

---

## 10. Boolean Data Type

Boolean represents **True or False**.

Example:

```python
x = True
y = False
```

Example:

```python
print(5 > 3)
```

Output:

```
True
```

Boolean values are widely used in **conditions and loops**.

---

## 11. Binary Data Types

Python supports binary data.

Types:

* bytes
* bytearray
* memoryview

Example:

```python
data = b"Hello"
print(data)
```

Output:

```
b'Hello'
```

Binary types are commonly used in **networking and file operations**.

---

## 12. None Type

`None` represents **absence of value**.

Example:

```python
x = None
print(type(x))
```

Output:

```
<class 'NoneType'>
```

Used when a variable **does not contain any value**.

Example:

```python
def func():
    pass

print(func())
```

Output:

```
None
```

---

## 13. Edge Cases

#### 1. Type conversion

Python allows converting between types.

Example:

```python
x = "10"
y = int(x)

print(y + 5)
```

Output:

```
15
```

---

#### 2. Mixed operations

```python
print(5 + 2.0)
```

Output:

```
7.0
```

Python automatically converts `int` → `float`.

---

#### 3. Immutable vs Mutable

Immutable types:

```
int
float
tuple
string
frozenset
```

Mutable types:

```
list
dict
set
```

---

## 14. Performance Considerations

Different data types affect **memory and speed**.

Example memory usage:

* `tuple` uses **less memory than list**
* `set` provides **fast lookup O(1)**

Example:

```python
numbers = [1,2,3]
```

Time complexity:

| Operation      | Complexity |
| -------------- | ---------- |
| List access    | O(1)       |
| Dict lookup    | O(1)       |
| Set membership | O(1)       |

---

## 15. Common Mistakes

#### Mistake 1

Mixing incompatible types.

```python
10 + "5"
```

Error:

```
TypeError
```

---

#### Mistake 2

Expecting list immutability.

```python
my_list = [1,2,3]
my_list[0] = 10
```

Lists **can change**.

---

#### Mistake 3

Modifying tuples.

```python
t = (1,2,3)
t[0] = 5
```

Error occurs.

---

## 16. Real World Usage

Example real program:

```python
student = {
    "name": "Alice",
    "age": 20,
    "marks": [85, 90, 88]
}

print(student["name"])
print(student["marks"][1])
```

Data types used:

* string
* integer
* list
* dictionary

---

## 17. Interview Questions

Basic:

1. What are data types in Python?
2. Is Python statically or dynamically typed?
3. What is the difference between list and tuple?

Intermediate:

4. What is mutable vs immutable?
5. What is the difference between set and dictionary?
6. What is None in Python?

Advanced:

7. How are Python objects stored internally?
8. Why are tuples faster than lists?
9. What is reference counting in Python?

---

## 18. Summary

Key points about **Python Data Types**:

* Data types define the **kind of data stored in variables**.
* Python is **dynamically typed**.
* Main categories include:

```
Numeric → int, float, complex
Text → str
Sequence → list, tuple, range
Mapping → dict
Set → set, frozenset
Boolean → bool
Binary → bytes, bytearray, memoryview
None → NoneType
```

Example recap:

```python
name = "Alice"
age = 25
marks = [80, 90, 85]
student = {"name": "Alice", "age": 25}
```

Each variable stores a **different data type**.

---

