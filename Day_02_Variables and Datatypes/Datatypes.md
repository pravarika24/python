# 📘 Day 02: Data Types in Python

> Data types define the kind of data a variable can store. Understanding data types helps you write efficient, reliable, and error-free Python programs.

---

## 📑 Table of Contents

- [Introduction to Data Types](#-introduction-to-data-types)
- [Definition of Data Types](#-definition-of-data-types)
- [Importance of Data Types](#-importance-of-data-types)
- [Basic Data Types](#-basic-data-types)
  - [Integer (int)](#-integer-int)
  - [Float (float)](#-float-float)
  - [String (str)](#-string-str)
  - [Boolean (bool)](#-boolean-bool)
- [Advanced Data Types](#-advanced-data-types)
- [Type Checking](#-type-checking)
- [Boolean Values](#-boolean-values)
- [Common Errors](#-common-errors)
- [Best Practices](#-best-practices)
- [Summary](#-summary)
- [Practice Exercises](#-practice-exercises)

---

![Variables and Data Types](images/ChatGPT%20Image%20Jul%203,%202026,%2006_36_02%20PM.png)

---

# 📖 Introduction to Data Types

Every value stored in Python has a **data type**.

A data type tells Python what kind of value a variable holds and what operations can be performed on that value.

Examples include numbers, text, and logical values.

[⬆ Back to Top](#-table-of-contents)

---

# 📝 Definition of Data Types

**Data types** are classifications of data that tell the Python interpreter how a programmer intends to use the data.

Data types determine:

- The kind of values a variable can store.
- The operations that can be performed on the data.
- The amount of memory required to store the data.

Example

```python
age = 23
name = "Prav"
height = 5.8
is_student = True
```

[⬆ Back to Top](#-table-of-contents)

---

# ⭐ Importance of Data Types

Data types play an important role in programming because they:

- Store data efficiently.
- Allow Python to perform the correct operations.
- Improve program performance.
- Help prevent errors and bugs.
- Make programs easier to understand and maintain.

[⬆ Back to Top](#-table-of-contents)

---

# 📌 Basic Data Types

Python provides several built-in data types.

| Data Type | Description | Example |
|-----------|-------------|---------|
| `int` | Integer numbers | `10` |
| `float` | Decimal numbers | `3.14` |
| `str` | Text or characters | `"Python"` |
| `bool` | Boolean values | `True`, `False` |

---

## 🔢 Integer (`int`)

Integers represent whole numbers.

```python
age = 23

print(type(age))
```

### Output

```
<class 'int'>
```

---

## 🔹 Float (`float`)

Floats represent decimal numbers.

```python
height = 3.5

print(type(height))
```

### Output

```
<class 'float'>
```

---

## 🔤 String (`str`)

Strings are sequences of characters enclosed in single or double quotes.

```python
name = "Prav"

print(type(name))
```

### Output

```
<class 'str'>
```

---

## ✅ Boolean (`bool`)

A Boolean value can only be either `True` or `False`.

```python
print(type(True))
```

Output

```
<class 'bool'>
```

Another example

```python
is_human = True

print(type(is_human))
```

Output

```
<class 'bool'>
```

Creating an empty Boolean:

```python
is_true = bool()

print(is_true)
```

Output

```
False
```

> **Note:** Calling `bool()` without any arguments returns `False`.

Boolean expressions also return Boolean values.

```python
a = 10
b = 10

print(a == b)
print(type(a == b))
```

Output

```
True
<class 'bool'>
```

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Advanced Data Types

Python also provides advanced data structures for storing collections of data.

| Data Type | Description |
|-----------|-------------|
| `list` | Ordered, mutable collection |
| `tuple` | Ordered, immutable collection |
| `set` | Unordered collection of unique elements |
| `dictionary` | Collection of key-value pairs |

Example

```python
fruits = ["Apple", "Banana", "Mango"]      # List

coordinates = (10, 20)                     # Tuple

colors = {"Red", "Green", "Blue"}          # Set

student = {
    "name": "Prav",
    "age": 23
}                                          # Dictionary
```

> **Note:** These advanced data types will be covered in detail in later chapters.

[⬆ Back to Top](#-table-of-contents)

---

# 🔍 Type Checking

Use the built-in `type()` function to determine the data type of a variable.

```python
age = 23
height = 3.5
name = "Prav"

print(type(age))
print(type(height))
print(type(name))
```

Output

```
<class 'int'>
<class 'float'>
<class 'str'>
```

[⬆ Back to Top](#-table-of-contents)

---

# ✔️ Boolean Values

Comparison operators return Boolean values.

```python
a = 10
b = 10

print(a == b)
```

Output

```
True
```

Another example

```python
print(10 > 20)
```

Output

```
False
```

[⬆ Back to Top](#-table-of-contents)

---

# ❌ Common Errors

## 1. Concatenating a String and an Integer

Incorrect

```python
result = "Hello" + 5
```

Output

```
TypeError
```

Reason:

Strings can only be concatenated with other strings.

Correct

```python
result = "Hello " + str(5)

print(result)
```

Output

```
Hello 5
```

---

## 2. Misspelled Function Name

Incorrect

```python
print(ype(is_human))
```

Correct

```python
print(type(is_human))
```

---

## 3. Using the Wrong Data Type

```python
age = "Twenty Three"

print(age + 5)
```

This raises a **TypeError** because a string cannot be added to an integer.

[⬆ Back to Top](#-table-of-contents)

---

# ✅ Best Practices

- Choose the correct data type for your data.
- Use meaningful variable names.
- Use `type()` to verify data types while learning.
- Convert data types when necessary using `int()`, `float()`, `str()`, and `bool()`.
- Avoid mixing incompatible data types.

Example

```python
age = 23
price = 199.99
name = "Prav"
is_student = True
```

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Summary

In this chapter, you learned:

- ✅ What data types are
- ✅ Why data types are important
- ✅ Basic Python data types
- ✅ Advanced Python data types
- ✅ Type checking using `type()`
- ✅ Boolean values
- ✅ Common data type errors
- ✅ Best practices

Understanding data types is essential because every value in Python belongs to a specific type, and choosing the right type leads to cleaner, safer, and more efficient programs.

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Practice Exercises

### Exercise 1

Create variables for the following data types:

- Integer
- Float
- String
- Boolean

Print the value and its data type.

---

### Exercise 2

Create:

- A list of your favorite fruits.
- A tuple containing three numbers.
- A set of programming languages.
- A dictionary containing your name and age.

---

### Exercise 3

Use `type()` to check the data type of:

```python
100
3.14
"Python"
False
```

---

### Exercise 4

Convert:

- Integer → Float
- Float → Integer
- Integer → String
- String → Boolean

Print the type after each conversion.

---

### Exercise 5

Fix the following code:

```python
result = "Age: " + 25

print(ype(result))
```

---

## 🎯 What's Next?

In the next chapter, you'll learn about:

- Variables
- Variable Naming Rules
- Type Conversion
- Dynamic Typing
- User Input

Happy Coding! 🚀