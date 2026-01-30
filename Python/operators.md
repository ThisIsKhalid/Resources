# ✅ 1) What is an Operator?

An **operator** is a symbol used to perform operations on values/variables.

Example:

```python
x = 10
y = 3
print(x + y)
```

---

# ✅ 2) Arithmetic Operators ✅

Used for math operations:

| Operator | Meaning             | Example       |
| -------- | ------------------- | ------------- |
| `+`      | addition            | `5 + 2 = 7`   |
| `-`      | subtraction         | `5 - 2 = 3`   |
| `*`      | multiplication      | `5 * 2 = 10`  |
| `/`      | division (float)    | `5 / 2 = 2.5` |
| `//`     | floor division      | `5 // 2 = 2`  |
| `%`      | modulus (remainder) | `5 % 2 = 1`   |
| `**`     | power               | `5 ** 2 = 25` |

### ✅ Example Code

```python
x = 10
y = 3

print(x + y)   # 13
print(x - y)   # 7
print(x * y)   # 30
print(x / y)   # 3.333...
print(x // y)  # 3
print(x % y)   # 1
print(x ** y)  # 1000
```

---

# ✅ 3) Assignment Operators ✅

Used to assign values

| Operator | Example  | Meaning     |
| -------- | -------- | ----------- |
| `=`      | `x = 10` | assign      |
| `+=`     | `x += 5` | `x = x + 5` |
| `-=`     | `x -= 5` | `x = x - 5` |
| `*=`     | `x *= 2` | `x = x * 2` |
| `/=`     | `x /= 2` | `x = x / 2` |

### ✅ Example

```python
x = 10
x += 5
print(x)  # 15
```

---

# ✅ 4) Comparison Operators ✅

Used for comparing values → returns **True/False**

| Operator | Meaning          | Example          |
| -------- | ---------------- | ---------------- |
| `==`     | equal            | `5 == 5 → True`  |
| `!=`     | not equal        | `5 != 3 → True`  |
| `>`      | greater          | `5 > 3 → True`   |
| `<`      | less             | `5 < 3 → False`  |
| `>=`     | greater or equal | `5 >= 5 → True`  |
| `<=`     | less or equal    | `5 <= 3 → False` |

### ✅ Example

```python
x = 10
y = 20

print(x == y)  # False
print(x < y)   # True
```

---

# ✅ 5) Logical Operators ✅

Used for combining multiple conditions:

| Operator | Meaning            |
| -------- | ------------------ |
| `and`    | both must be True  |
| `or`     | any one True       |
| `not`    | reverse the result |

### ✅ Example

```python
age = 25
has_id = True

print(age > 18 and has_id)  # True
```

---

# ✅ 6) Membership Operators ✅

Checks if something exists in a list/string

| Operator | Meaning       |
| -------- | ------------- |
| `in`     | exists        |
| `not in` | doesn't exist |

### ✅ Example

```python
fruits = ["apple", "banana", "mango"]

print("apple" in fruits)      # True
print("orange" not in fruits) # True
```

---

# ✅ 7) Identity Operators ✅

Checks if two variables are the **same object in memory**

| Operator | Meaning         |
| -------- | --------------- |
| `is`     | same object     |
| `is not` | not same object |

### ✅ Example

```python
x = [1, 2]
y = [1, 2]

print(x == y)  # True  (same value)
print(x is y)  # False (different memory)
```

✅ `==` checks value
✅ `is` checks memory/reference

---

# ✅ Practice Task ✅

Take 2 numbers from user and print:

✅ sum
✅ difference
✅ multiplication
✅ division
✅ remainder (`%`)
✅ power (`**`)

Example output:

```
Sum: 15
Difference: 5
Multiply: 50
Divide: 2.0
Remainder: 0
Power: 100000
```

