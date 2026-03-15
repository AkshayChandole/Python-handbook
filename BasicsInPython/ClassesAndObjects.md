# [Classes and Objects](#Classes-and-Objects)

## 1. Topic Overview

**Classes and Objects** are the core concepts of **Object-Oriented Programming (OOP)** in Python.

* A **Class** is a blueprint or template for creating objects.
* An **Object** is an instance of a class.

In simple terms:

> **A class defines properties and behavior, and objects represent real-world entities created from that class.**

Example:

```python id="coz7a3"
class Car:
    pass

my_car = Car()
```

Here:

* `Car` → class
* `my_car` → object of class `Car`

Classes allow programmers to **organize code and model real-world entities**.

---

## 2. Problem it Solves

Without classes, managing complex programs becomes difficult.

Example without classes:

```python id="v5lsp6"
name = "Alice"
age = 20
marks = 85
```

If we have **100 students**, we would need hundreds of variables.

Using classes:

```python id="2v72r5"
class Student:
    pass
```

Objects:

```python id="kg9o8r"
s1 = Student()
s2 = Student()
```

Classes help:

* organize data
* reuse code
* create multiple objects easily
* model real-world systems

---

## 3. Concept Explanation

In OOP, classes define:

1. **Attributes (Data)**
2. **Methods (Functions)**

Example:

```python id="vt0hmt"
class Student:
    name = "Alice"
```

Here:

* `Student` → class
* `name` → attribute

Example with method:

```python id="xnbb1f"
class Student:
    
    def greet(self):
        print("Hello Student")
```

Objects can access methods.

---

### Creating Objects

Objects are created using the class name.

```python id="sczy5z"
s1 = Student()
```

`Student()` calls the **class constructor**.

---

## 4. Internal Working

Internally, Python classes are **objects themselves**.

When Python executes:

```python id="mfknm1"
class Student:
    pass
```

Python performs:

1. Creates a **class object**
2. Stores attributes and methods in a **dictionary**
3. Assigns class name `Student` to the object

Example internal structure:

```
Student
   |
   └── __dict__
        ├── methods
        └── attributes
```

Creating object:

```python id="k7hujr"
s1 = Student()
```

Python:

1. Allocates memory
2. Creates object instance
3. Links it to class

Memory representation:

```
s1 → Student instance
```

---

## 5. Syntax

#### Class Syntax

```python id="xqkzzc"
class ClassName:
    attributes
    methods
```

Example:

```python id="sv6tk2"
class Person:
    pass
```

---

#### Object Creation

```
object_name = ClassName()
```

Example:

```python id="iy0l9m"
p1 = Person()
```

---

## 6. Code Examples

---

## Example 1 — Simple Class

```python id="t3pf6x"
class Dog:
    pass

d1 = Dog()

print(type(d1))
```

Output:

```
<class '__main__.Dog'>
```

---

## Example 2 — Class with Attribute

```python id="c7kkn8"
class Student:
    name = "Alice"

s1 = Student()

print(s1.name)
```

Output:

```
Alice
```

---

## Example 3 — Class with Method

```python id="9fbw9m"
class Student:
    
    def greet(self):
        print("Hello")

s1 = Student()
s1.greet()
```

Output:

```
Hello
```

---

## Example 4 — Constructor (`__init__`)

`__init__` initializes objects.

```python id="k8msdl"
class Student:

    def __init__(self, name):
        self.name = name

s1 = Student("Alice")

print(s1.name)
```

Output:

```
Alice
```

---

## Example 5 — Multiple Objects

```python id="qd9wba"
class Student:

    def __init__(self, name):
        self.name = name

s1 = Student("Alice")
s2 = Student("Bob")

print(s1.name)
print(s2.name)
```

Output:

```
Alice
Bob
```

Each object stores **its own data**.

---

## 7. Edge Cases

#### Accessing attributes

```python id="3sgizk"
class Test:
    x = 10

t = Test()
print(t.x)
```

Python first searches:

1. Object attributes
2. Class attributes

---

#### Dynamic attributes

Python allows adding attributes dynamically.

```python id="ukmocq"
class Student:
    pass

s = Student()
s.age = 20

print(s.age)
```

Output:

```
20
```

---

#### Shared class attributes

```python id="n0hpxu"
class Counter:
    count = 0

c1 = Counter()
c2 = Counter()

print(c1.count)
print(c2.count)
```

Output:

```
0
0
```

Both objects share the same class variable.

---

## 8. Performance Considerations

Creating objects consumes memory.

Example:

```python id="f0m9hb"
class A:
    pass
```

Every instance stores:

* object header
* attribute dictionary
* references

To reduce memory usage, Python provides **`__slots__`**.

Example:

```python id="l1ibzq"
class Student:
    __slots__ = ['name']
```

This avoids creating `__dict__`.

Benefits:

* lower memory
* faster attribute access

---

## 9. Common Mistakes

#### Missing `self`

Wrong:

```python id="20qf3b"
class Test:

    def greet():
        print("Hello")
```

Correct:

```python id="6h8s8a"
class Test:

    def greet(self):
        print("Hello")
```

---

#### Forgetting object creation

Wrong:

```python id="1i20q7"
Student.greet()
```

Correct:

```python id="rs0n9o"
s = Student()
s.greet()
```

---

#### Confusing class and instance variables

```python id="45zj1a"
class Test:
    x = 10
```

`x` belongs to the **class**, not the object.

---

## 10. Real World Usage

Classes model real-world objects.

Example: bank account system.

```python id="ctm64o"
class BankAccount:

    def __init__(self, name, balance):
        self.name = name
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount

acc = BankAccount("Alice",1000)

acc.deposit(500)

print(acc.balance)
```

Output:

```
1500
```

Classes are used in:

* web frameworks
* machine learning libraries
* game development
* APIs
* database models

---

## 11. Interview Questions

#### Basic

1. What is a class in Python?
2. What is an object?
3. What is the difference between class and object?

#### Intermediate

4. What is `__init__()`?
5. What is `self`?
6. Difference between class variable and instance variable?

#### Advanced

7. How does Python create objects internally?
8. What is `__dict__`?
9. What are slots in Python classes?

---

## 12. Summary

Key points:

* **Class** → blueprint for objects
* **Object** → instance of class

Basic syntax:

```python id="tv2hnr"
class ClassName:
    pass

obj = ClassName()
```

Classes contain:

```
attributes
methods
constructors
```

Example recap:

```python id="n2hx1s"
class Student:

    def __init__(self,name):
        self.name = name

s = Student("Alice")

print(s.name)
```

Output:

```
Alice
```

Classes and objects allow Python programs to be **structured, reusable, and scalable**.

---
