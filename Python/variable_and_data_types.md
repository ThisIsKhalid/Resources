# ✅ 1) Variables in Python

A **variable** is a name that stores a value in memory.

### ✅ Example

```python
name = "Khalid"
age = 23
is_student = True
```

### ✅ Rules for Variable Names

✅ Allowed:

* letters (a-z, A-Z)
* numbers (0-9) **but not at the beginning**
* underscore `_`

✅ Good examples:

```python
user_name = "Hasan"
age2 = 25
_total_price = 500
```

❌ Bad examples:

```python
2age = 20      # ❌ cannot start with number
user-name = "" # ❌ "-" not allowed
class = "abc"  # ❌ reserved keyword
```

✅ Python variable naming style (best practice):
✅ **snake_case**

```python
first_name = "Khalid"
account_balance = 1000
```

---

# ✅ 2) Data Types in Python

Python has different types of values.

---

## ✅ A) int (Integer)

Whole numbers (no decimal)

```python
x = 10
y = -50
print(type(x))
```

✅ Output:

```
<class 'int'>
```

---

## ✅ B) float (Decimal numbers)

Numbers with decimal points

```python
price = 99.99
pi = 3.1416
print(type(price))
```

✅ Output:

```
<class 'float'>
```

---

## ✅ C) str (String)

Text inside quotes

```python
name = "Khalid"
msg = 'Hello Python'
print(type(name))
```

✅ Output:

```
<class 'str'>
```

✅ Strings can contain numbers too:

```python
phone = "01700000000"
```

This is still a **string**, not number.

---

## ✅ D) bool (Boolean)

Only 2 values:

✅ `True` or `False`

```python
is_logged_in = True
is_admin = False
print(type(is_logged_in))
```

✅ Output:

```
<class 'bool'>
```

---

## ✅ E) NoneType

Represents “nothing / empty value”

```python
value = None
print(type(value))
```

✅ Output:

```
<class 'NoneType'>
```

---

# ✅ 3) Checking Data Type

Use `type()`

```python
x = 100
print(type(x))  # int
```

---

# ✅ 4) Changing Data Types (Type Casting)

### ✅ str → int

```python
age = "25"
age_number = int(age)
print(age_number + 5)  # 30
```

### ✅ int → str

```python
number = 100
text = str(number)
print(text)
```

### ✅ int → float

```python
x = 10
y = float(x)
print(y)  # 10.0
```

---

# ✅ 5) Common Beginner Mistake ⚠️

### ❌ This will crash:

```python
x = "10"
y = 5
print(x + y)
```

✅ Error:
`TypeError: can only concatenate str (not "int") to str`

✅ Fix:

```python
x = "10"
y = 5
print(int(x) + y)  # 15
```

---

# ✅ 6) Quick Summary (Super Important ✅)

| Type       | Meaning      | Example   |
| ---------- | ------------ | --------- |
| `int`      | whole number | `10`      |
| `float`    | decimal      | `10.5`    |
| `str`      | text         | `"hello"` |
| `bool`     | true/false   | `True`    |
| `NoneType` | empty        | `None`    |

---

# ✅ Practice Task (Must Do ✅)

Write a Python program that stores these values and prints them:

✅ name = your name (string)
✅ age = your age (int)
✅ height = your height (float)
✅ is_developer = True/False (bool)

Example output:

```
Name: Khalid
Age: 23
Height: 5.8
Developer: True
```