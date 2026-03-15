# [Operators](#Operators)


## 1. Topic Overview

**Operators** in Python are **symbols or keywords used to perform operations on variables and values**.

In simple terms:

> **Operators tell Python what action to perform on data.**

Example:

```python
x = 10
y = 5
print(x + y)
```

Here:

* `+` is an **operator**
* It performs **addition**

Output:

```
15
```

Operators are used in almost every Python program for:

* mathematical calculations
* comparisons
* logical decisions
* data manipulation

---

## 2. Problem it Solves

Without operators, performing operations on data would be impossible.

Example problem:

Imagine trying to add two numbers without operators.

```
10 ? 5
```

Python wouldn't know what action to perform.

Operators solve this by defining operations such as:

| Operation         | Operator       |
| ----------------- | -------------- |
| Addition          | `+`            |
| Subtraction       | `-`            |
| Multiplication    | `*`            |
| Division          | `/`            |
| Comparison        | `>`, `<`, `==` |
| Logical decisions | `and`, `or`    |

Example:

```python
price = 100
tax = 10

total = price + tax
print(total)
```

Output:

```
110
```

The `+` operator performs the calculation.

---

## 3. Concept Explanation

Python provides **different types of operators**.

Main categories:

| Operator Type        | Examples          |            |
| -------------------- | ----------------- | ---------- |
| Arithmetic Operators | `+ - * / % ** //` |            |
| Comparison Operators | `== != > < >= <=` |            |
| Assignment Operators | `= += -= *=`      |            |
| Logical Operators    | `and or not`      |            |
| Bitwise Operators    | `&                | ^ ~ << >>` |
| Membership Operators | `in`, `not in`    |            |
| Identity Operators   | `is`, `is not`    |            |

Each category performs **different operations on data**.

---

## 4. Internal Working

Internally, Python operators call **special methods (magic methods)**.

Example:

```python
x = 10
y = 5

x + y
```

Python internally performs:

```
x.__add__(y)
```

Similarly:

| Operator | Internal Method |
| -------- | --------------- |
| `+`      | `__add__()`     |
| `-`      | `__sub__()`     |
| `*`      | `__mul__()`     |
| `/`      | `__truediv__()` |

Example:

```python
print(int.__add__(10, 5))
```

Output:

```
15
```

So operators are **syntactic shortcuts for method calls**.

---

## 5. Arithmetic Operators

Arithmetic operators perform **mathematical calculations**.

| Operator | Meaning        |
| -------- | -------------- |
| `+`      | Addition       |
| `-`      | Subtraction    |
| `*`      | Multiplication |
| `/`      | Division       |
| `%`      | Modulus        |
| `**`     | Power          |
| `//`     | Floor division |

---

### Example 1

```python
a = 10
b = 3

print(a + b)
print(a - b)
print(a * b)
```

Output:

```
13
7
30
```

---

### Example 2

```python
print(10 / 3)
print(10 // 3)
print(10 % 3)
```

Output:

```
3.3333333333
3
1
```

Explanation:

* `/` → division
* `//` → floor division
* `%` → remainder

---

### Example 3 (Power)

```python
print(2 ** 3)
```

Output:

```
8
```

---

## 6. Comparison Operators

Comparison operators compare two values and return **True or False**.

| Operator | Meaning          |
| -------- | ---------------- |
| `==`     | Equal            |
| `!=`     | Not equal        |
| `>`      | Greater than     |
| `<`      | Less than        |
| `>=`     | Greater or equal |
| `<=`     | Less or equal    |

---

Example:

```python
x = 10
y = 5

print(x > y)
print(x == y)
```

Output:

```
True
False
```

---

## 7. Assignment Operators

Assignment operators assign values to variables.

| Operator | Example  |
| -------- | -------- |
| `=`      | `x = 10` |
| `+=`     | `x += 5` |
| `-=`     | `x -= 3` |
| `*=`     | `x *= 2` |
| `/=`     | `x /= 4` |

---

Example:

```python
x = 10
x += 5

print(x)
```

Output:

```
15
```

Equivalent to:

```
x = x + 5
```

---

## 8. Logical Operators

Logical operators combine **boolean expressions**.

| Operator | Meaning               |
| -------- | --------------------- |
| `and`    | True if both are true |
| `or`     | True if one is true   |
| `not`    | Reverses result       |

---

Example:

```python
x = 10

print(x > 5 and x < 20)
```

Output:

```
True
```

---

Example:

```python
print(True or False)
print(not True)
```

Output:

```
True
False
```

---

## 9. Bitwise Operators

Bitwise operators work on **binary numbers**.

| Operator | Meaning     |    |
| -------- | ----------- | -- |
| `&`      | AND         |    |
| `        | `           | OR |
| `^`      | XOR         |    |
| `~`      | NOT         |    |
| `<<`     | Left shift  |    |
| `>>`     | Right shift |    |

Example:

```python
print(5 & 3)
```

Binary:

```
5 → 101
3 → 011
---------
    001
```

Output:

```
1
```

---

## 10. Membership Operators

Membership operators check if a value exists in a sequence.

| Operator | Meaning              |
| -------- | -------------------- |
| `in`     | Value exists         |
| `not in` | Value does not exist |

---

Example:

```python
numbers = [1,2,3,4]

print(3 in numbers)
print(5 in numbers)
```

Output:

```
True
False
```

---

## 11. Identity Operators

Identity operators compare **memory locations** of objects.

| Operator | Meaning          |
| -------- | ---------------- |
| `is`     | Same object      |
| `is not` | Different object |

---

Example:

```python
a = [1,2]
b = a

print(a is b)
```

Output:

```
True
```

Both variables refer to **same object in memory**.

---

Example:

```python
a = [1,2]
b = [1,2]

print(a is b)
```

Output:

```
False
```

Different objects even though values are same.

---

## 12. Edge Cases

#### String operators

```python
print("Hello" + " World")
```

Output:

```
Hello World
```

---

#### String repetition

```python
print("Hi" * 3)
```

Output:

```
HiHiHi
```

---

#### List concatenation

```python
print([1,2] + [3,4])
```

Output:

```
[1, 2, 3, 4]
```

---

## 13. Performance Considerations

Some operators are **faster than function calls**.

Example:

```python
x + y
```

is faster than:

```
add(x, y)
```

Bitwise operators are extremely fast because they operate **directly on binary values**.

Example:

```
x << 1
```

is faster than:

```
x * 2
```

in some low-level cases.

---

## 14. Common Mistakes

#### Mistake 1 — Using `=` instead of `==`

Wrong:

```python
if x = 5:
```

Error occurs.

Correct:

```python
if x == 5:
```

---

#### Mistake 2 — Confusing `is` with `==`

`==` compares values.

`is` compares memory location.

Example:

```python
a = [1,2]
b = [1,2]

print(a == b)
print(a is b)
```

Output:

```
True
False
```

---

#### Mistake 3 — Division confusion

```
/  → float division
// → floor division
```

Example:

```python
print(5/2)
print(5//2)
```

Output:

```
2.5
2
```

---

## 15. Real World Usage

Example program:

```python
price = 100
tax = 18

total = price + (price * tax / 100)

if total > 100:
    print("Total price:", total)
```

Operators used:

* `+`
* `*`
* `/`
* `>`
* `=`

Operators allow programs to **perform logic, calculations, and decisions**.

---

## 16. Interview Questions

Basic:

1. What are operators in Python?
2. How many types of operators exist in Python?

Intermediate:

3. Difference between `==` and `is`?
4. What is floor division?

Advanced:

5. How does Python implement operators internally?
6. What are magic methods like `__add__`?
7. Explain bitwise operators.

---

## 17. Summary

Key points about **Python Operators**:

* Operators perform **actions on variables and values**.
* Python has **7 main operator categories**.

Main operators:

```
Arithmetic → + - * / % ** //
Comparison → == != > < >= <=
Assignment → = += -= *=
Logical → and or not
Bitwise → & | ^ ~ << >>
Membership → in not in
Identity → is is not
```

Example recap:

```python
x = 10
y = 5

print(x + y)
print(x > y)
print(x == y)
```

Output:

```
15
True
False
```

Operators are **fundamental to all Python programs**.

---
