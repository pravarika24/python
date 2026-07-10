# 📘 Day 02: Variables in Python

> Variables are one of the fundamental concepts in Python. They are used to store data that can be referenced and manipulated throughout a program.

---

## 📑 Table of Contents

- [Introduction to Variables](#-introduction-to-variables)
- [Declaring and Assigning Variables](#-declaring-and-assigning-variables)
- [Printing Variables](#-printing-variables)
- [Variable Naming Conventions](#-variable-naming-conventions)
  - [Valid Variable Names](#-valid-variable-names)
  - [Invalid Variable Names](#-invalid-variable-names)
- [Understanding Variable Types](#-understanding-variable-types)
- [Type Checking](#-type-checking)
- [Type Conversion](#-type-conversion)
- [Dynamic Typing](#-dynamic-typing)
- [Taking Input from the User](#-taking-input-from-the-user)
- [Common Errors](#-common-errors)
- [Best Practices](#-best-practices)
- [Summary](#-summary)
- [Practice Exercises](#-practice-exercises)

---

![Variables and Data Types](images/ChatGPT%20Image%20Jul%203,%202026,%2006_36_02%20PM.png)

---

# 📖 Introduction to Variables

Variables are fundamental elements in programming used to **store data** that can be referenced and manipulated throughout a program.

In Python, variables are created automatically when a value is assigned to them. Unlike many programming languages, Python does **not** require explicit variable declarations or memory allocation.

```python
name = "Prav"
age = 27
height = 5.4
```

> **Note:** Python automatically determines the data type of a variable based on the assigned value.

[⬆ Back to Top](#-table-of-contents)

---

# ✍️ Declaring and Assigning Variables

Variables are created using the assignment operator (`=`).

```python
age = 27
height = 5.4
name = "Prav"
```

Here,

- `age` stores an integer.
- `height` stores a floating-point number.
- `name` stores a string.

[⬆ Back to Top](#-table-of-contents)

---

# 🖨️ Printing Variables

The `print()` function is used to display variable values.

```python
age = 27
height = 5.4
name = "Prav"

print("Age:", age)
print("Height:", height)
print("Name:", name)
```

### Output

```
Age: 27
Height: 5.4
Name: Prav
```

> **Note:** Your original code contained a small syntax error:
>
> ❌ `print("name":,name)`
>
> ✅ `print("Name:", name)`

[⬆ Back to Top](#-table-of-contents)

---

# 🏷️ Variable Naming Conventions

Choosing meaningful variable names makes your code easier to read and maintain.

## Rules

- Variable names should be descriptive.
- They must begin with a letter (`A-Z` or `a-z`) or an underscore (`_`).
- They can contain letters, numbers, and underscores.
- They **cannot** start with a number.
- They cannot contain spaces or special characters.
- Variable names are **case-sensitive**.

Example

```python
first_name = "Prav"
last_name = "Kosanam"
student_age = 27
_course = "Python"
```

[⬆ Back to Top](#-table-of-contents)

---

## ✅ Valid Variable Names

```python
first_name = "Prav"
last_name = "Kosanam"
student_age = 25
course1 = "Python"
_marks = 95
```

---

## ❌ Invalid Variable Names

```python
5name = "Prav"
first-name = "Kosanam"
@name = "Kosa"
my name = "Prav"
```

Why are these invalid?

- Starts with a number ❌
- Contains a hyphen (`-`) ❌
- Uses special characters (`@`) ❌
- Contains spaces ❌

[⬆ Back to Top](#-table-of-contents)

---

# 🔍 Understanding Variable Types

Python is a **dynamically typed** programming language.

The data type of a variable is determined automatically when a value is assigned.

```python
age = 27
height = 6.1
name = "Prav"

print(type(age))
print(type(height))
print(type(name))
```

### Output

```
<class 'int'>
<class 'float'>
<class 'str'>
```

[⬆ Back to Top](#-table-of-contents)

---

# 🔎 Type Checking

The built-in `type()` function is used to determine the data type of a variable.

```python
height = 5.4

print(type(height))
```

Output

```
<class 'float'>
```

Another example

```python
age = 27

print(type(age))
```

Output

```
<class 'int'>
```

[⬆ Back to Top](#-table-of-contents)

---

# 🔄 Type Conversion

Python allows conversion from one data type to another using built-in functions such as `int()`, `float()`, `str()`, and `bool()`.

### Integer to String

```python
age = 27

age_str = str(age)

print(type(age))
print(type(age_str))
```

Output

```
<class 'int'>
<class 'str'>
```

### Invalid Conversion

```python
name = "Prav"

int(name)
```

Output

```
ValueError: invalid literal for int()
```

> **Note:** A non-numeric string cannot be converted into an integer or float.

[⬆ Back to Top](#-table-of-contents)

---

# 🔄 Dynamic Typing

Python allows a variable to change its data type during program execution.

```python
var = 10

print(var, type(var))
```

Output

```
10 <class 'int'>
```

The same variable can later store a string.

```python
var = "Hello"

print(var, type(var))
```

Output

```
Hello <class 'str'>
```

It can even store a floating-point value.

```python
var = 11.5

print(var, type(var))
```

Output

```
11.5 <class 'float'>
```

This feature is called **Dynamic Typing**.

[⬆ Back to Top](#-table-of-contents)

---

# ⌨️ Taking Input from the User

The `input()` function is used to receive input from the user.

```python
age = input("Enter your age: ")

print(type(age))
```

Output

```
<class 'str'>
```

Notice that the `input()` function always returns a **string**.

To use the value as an integer, convert it using `int()`.

```python
age = int(input("Enter your age: "))

print(type(age))
```

Output

```
<class 'int'>
```

> **Tip:** Always convert numeric input before performing arithmetic operations.

[⬆ Back to Top](#-table-of-contents)

---

# ❌ Common Errors

### 1. Invalid Variable Name

```python
5name = "Prav"
```

**Error:** Variable names cannot start with a number.

---

### 2. Using Special Characters

```python
first-name = "Prav"
```

**Error:** Hyphen (`-`) is treated as the subtraction operator.

---

### 3. Invalid Type Conversion

```python
name = "Prav"

int(name)
```

**Error:** Non-numeric strings cannot be converted into integers.

---

### 4. Forgetting to Convert User Input

```python
age = input("Enter your age: ")

print(age + 5)
```

This raises a `TypeError`.

Correct version:

```python
age = int(input("Enter your age: "))

print(age + 5)
```

[⬆ Back to Top](#-table-of-contents)

---

# ✅ Best Practices

- Use meaningful variable names.
- Follow the **snake_case** naming convention.
- Avoid single-letter variable names unless necessary.
- Convert user input before calculations.
- Use `type()` while learning to understand data types.
- Keep variable names descriptive and readable.

Example

```python
student_name = "Prav"
student_age = 27
course_name = "Python Programming"
```

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Summary

In this chapter, you learned:

- ✅ What variables are
- ✅ Declaring and assigning variables
- ✅ Printing variables
- ✅ Variable naming conventions
- ✅ Valid and invalid variable names
- ✅ Understanding variable types
- ✅ Type checking
- ✅ Type conversion
- ✅ Dynamic typing
- ✅ Taking input from users
- ✅ Common errors and best practices

Variables are the foundation of Python programming and are used in almost every program to store and manipulate data.

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Practice Exercises

### Exercise 1

Create variables to store:

- Your name
- Your age
- Your city

Print all the values.

---

### Exercise 2

Create variables for the following data types:

- Integer
- Float
- String
- Boolean

Print both the value and its data type.

---

### Exercise 3

Check the type of:

```python
100
3.14
"Python"
True
```

---

### Exercise 4

Convert:

- Integer → String
- Integer → Float
- Float → Integer

Print the data type after each conversion.

---

### Exercise 5

Take the user's age as input and print the age after **10 years**.

Example

```
Enter your age: 25

After 10 years, your age will be: 35
```

---

## 🎯 What's Next?

In **Day 03**, you'll learn about:

- Arithmetic Operators
- Comparison Operators
- Logical Operators
- Operator Precedence

Happy Coding! 🚀
