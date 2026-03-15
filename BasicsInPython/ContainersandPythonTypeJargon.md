# [Containers and Python Type Jargon](#Containers-and-Python-Type-Jargon)


## 1. Topic Overview

In Python, **containers** are data types that can **store multiple values inside a single object**.

Python also uses specific terminology called **type jargon** to describe characteristics of these data structures, such as whether they are:

* Mutable
* Immutable
* Ordered
* Iterable
* Hashable

In simple terms:

> **Containers are objects that hold other objects.**

Example:

```python
numbers = [1, 2, 3, 4]
```

Here:

* `numbers` is a **container**
* It contains **four elements**

Common Python containers:

| Container Type | Example          |
| -------------- | ---------------- |
| List           | `[1,2,3]`        |
| Tuple          | `(1,2,3)`        |
| Set            | `{1,2,3}`        |
| Dictionary     | `{"a":1, "b":2}` |
| String         | `"Python"`       |

---

## 2. Problem it Solves

Programs often need to **store collections of data**.

Example problems:

* Store list of students
* Store product prices
* Store user information
* Store database records

Without containers:

```python
a = 10
b = 20
c = 30
d = 40
```

With containers:

```python
numbers = [10,20,30,40]
```

Containers allow:

* grouping data
* easier iteration
* efficient memory management
* simplified algorithms

---

## 3. Concept Explanation

Python containers store **multiple objects in a structured format**.

#### Major container types

| Container  | Description                  |
| ---------- | ---------------------------- |
| List       | Ordered mutable sequence     |
| Tuple      | Ordered immutable sequence   |
| Set        | Unordered unique elements    |
| Dictionary | Key-value mapping            |
| String     | Immutable character sequence |

Example:

```python
data = [10, "Alice", 3.5]
```

Python containers can store **mixed data types**.

---

## 4. Internal Working

In Python, containers store **references to objects**, not the objects themselves.

Example:

```python
x = 10
y = 20

numbers = [x, y]
```

Memory representation:

```
numbers
   ↓
[ ref → 10 , ref → 20 ]
```

Each container element holds a **pointer to an object in memory**.

This allows:

* dynamic typing
* heterogeneous containers

Example:

```python
items = [1, "Python", 3.14]
```

Each element points to a different object type.

---

## 5. Container Syntax

#### List

```python
list_name = [value1, value2, value3]
```

Example:

```python
numbers = [1,2,3]
```

---

#### Tuple

```python
tuple_name = (value1, value2)
```

Example:

```python
point = (10,20)
```

---

#### Set

```python
set_name = {value1, value2}
```

Example:

```python
unique = {1,2,3}
```

---

#### Dictionary

```python
dict_name = {key:value}
```

Example:

```python
student = {"name":"Alice", "age":20}
```

---

## 6. Code Examples

---

### Example 1 — List Container

```python
numbers = [10,20,30]

print(numbers[1])
```

Output

```
20
```

Lists are **ordered and mutable**.

---

### Example 2 — Tuple Container

```python
coordinates = (10,20)

print(coordinates[0])
```

Output

```
10
```

Tuples are **immutable**.

---

### Example 3 — Set Container

```python
numbers = {1,2,2,3}

print(numbers)
```

Output

```
{1,2,3}
```

Sets remove duplicates.

---

### Example 4 — Dictionary Container

```python
student = {"name":"John", "age":21}

print(student["name"])
```

Output

```
John
```

Dictionaries store **key-value pairs**.

---

## 7. Python Type Jargon

Python uses terminology to describe properties of types.

---

## Mutable vs Immutable

#### Mutable

Objects that **can change after creation**.

Examples:

```
list
set
dict
bytearray
```

Example:

```python
numbers = [1,2,3]

numbers[0] = 10
print(numbers)
```

Output

```
[10,2,3]
```

---

#### Immutable

Objects that **cannot change after creation**.

Examples:

```
int
float
tuple
str
frozenset
```

Example:

```python
text = "Python"
text[0] = "J"
```

Error occurs.

---

## Ordered vs Unordered

#### Ordered

Elements maintain **fixed order**.

Examples:

```
list
tuple
string
```

Example:

```python
numbers = [5,10,15]
```

Position matters.

---

#### Unordered

Elements have **no guaranteed order**.

Examples:

```
set
dict (before Python 3.7)
```

Example:

```python
{1,5,3}
```

---

## Iterable

An object is **iterable** if it can be looped through.

Examples:

```
list
tuple
set
string
dictionary
range
```

Example:

```python
numbers = [1,2,3]

for n in numbers:
    print(n)
```

Output

```
1
2
3
```

---

## Sequence

Sequences support:

```
indexing
slicing
ordering
```

Examples:

```
list
tuple
string
range
```

Example:

```python
text = "Python"
print(text[0])
```

Output

```
P
```

---

## Hashable

Hashable objects have a **fixed hash value** and can be used as dictionary keys.

Examples:

```
int
str
tuple
frozenset
```

Example:

```python
data = { "name": "Alice" }
```

`"name"` is hashable.

Not hashable:

```
list
set
dict
```

Example:

```python
data = {[1,2]: "value"}
```

Error occurs.

---

## 8. Edge Cases

#### List inside tuple

```python
t = ([1,2], 3)

t[0][0] = 10
print(t)
```

Output

```
([10,2], 3)
```

Even though tuple is immutable, contained objects may still change.

---

#### Dictionary keys must be hashable

Valid:

```python
data = {(1,2): "point"}
```

Invalid:

```python
data = {[1,2]: "point"}
```

Lists are not hashable.

---

## 9. Performance Considerations

Different containers have different complexities.

| Operation | List | Dict | Set  |
| --------- | ---- | ---- | ---- |
| Access    | O(1) | O(1) | O(1) |
| Search    | O(n) | O(1) | O(1) |
| Insert    | O(1) | O(1) | O(1) |

Example:

Dictionary lookup:

```python
student["name"]
```

Fast because dictionaries use **hash tables**.

---

## 10. Common Mistakes

#### Confusing mutable and immutable

Example:

```python
x = 10
x += 1
```

This creates a **new integer object**.

---

#### Using mutable objects as dictionary keys

Wrong:

```python
data = {[1,2]: "value"}
```

Lists are not hashable.

---

#### Expecting order in sets

```python
print({3,1,2})
```

Order may change.

---

## 11. Real World Usage

Containers are used everywhere.

Example: student database.

```python
students = [
    {"name":"Alice", "age":20},
    {"name":"Bob", "age":22}
]

for s in students:
    print(s["name"])
```

Output

```
Alice
Bob
```

Used in:

* databases
* APIs
* data science
* machine learning
* web frameworks

---

## 12. Interview Questions

Basic:

1. What are containers in Python?
2. Name Python container types.

Intermediate:

3. Difference between mutable and immutable types.
4. What is iterable in Python?

Advanced:

5. What makes an object hashable?
6. Why can tuples be dictionary keys but lists cannot?
7. Explain Python container memory model.

---

## 13. Summary

Key points:

Containers are **objects that store multiple elements**.

Main Python containers:

```
list
tuple
set
dictionary
string
```

Important type terminology:

| Term      | Meaning               |
| --------- | --------------------- |
| Mutable   | Can change            |
| Immutable | Cannot change         |
| Ordered   | Maintains order       |
| Iterable  | Can loop over         |
| Sequence  | Supports indexing     |
| Hashable  | Can be dictionary key |

Example recap:

```python
data = [1,2,3]

for item in data:
    print(item)
```

Containers are fundamental to **data organization and algorithm design in Python**.

---

