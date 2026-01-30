# ✅ 1) Output in Python (`print()`)

### ✅ Basic print

```python
print("Hello Python")
print(100)
print(True)
```

### ✅ Print multiple things

```python
name = "Khalid"
age = 23

print(name, age)
```

✅ Output:

```
Khalid 23
```

---

# ✅ 2) Printing with f-string (Best Practice ✅)

✅ Professional way:

```python
name = "Khalid"
age = 23

print(f"My name is {name} and I am {age} years old.")
```

---

# ✅ 3) Taking Input (`input()`)

`input()` always returns a **string**.

```python
name = input("Enter your name: ")
print(name)
```

✅ Example run:

```
Enter your name: Khalid
Khalid
```

---

# ✅ 4) Input + Type Conversion (Very Important ✅)

### ✅ Input for int

```python
age = int(input("Enter your age: "))
print(age)
print(type(age))
```

✅ Example:

```
Enter your age: 25
<class 'int'>
```

---

### ✅ Input for float

```python
height = float(input("Enter your height: "))
print(height)
```

Example:

```
Enter your height: 5.8
```

---

# ✅ 5) Full Example Program

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))
country = input("Enter your country: ")

print(f"Hello {name} 👋")
print(f"Your age is {age}")
print(f"You live in {country}")
```

---

# ✅ 6) Common Mistake ⚠️

### ❌ Wrong

```python
x = input("Enter number 1: ")
y = input("Enter number 2: ")

print(x + y)
```

If you input `10` and `20`, output হবে:

```
1020
```

✅ Because input is string, so it's doing **string concatenation**

---

### ✅ Correct

```python
x = int(input("Enter number 1: "))
y = int(input("Enter number 2: "))

print(x + y)
```

Output:

```
30
```

---

# ✅ Practice Task (Do it ✅)

Write a program that:
✅ takes 2 numbers input
✅ prints sum, subtraction, multiplication, division

Expected output format:

```
Sum: 30
Subtract: 10
Multiply: 200
Divide: 2.0
```
