# 📘 Day 07: Python Standard Library Overview

> Python's Standard Library is a collection of built-in modules and packages that come bundled with Python. These modules provide a wide range of functionalities, allowing developers to perform common programming tasks without installing external libraries.

---

## 📑 Table of Contents

- [Introduction to the Standard Library](#-introduction-to-the-standard-library)
- [The `array` Module](#-the-array-module)
- [The `math` Module](#-the-math-module)
- [The `random` Module](#-the-random-module)
- [The `os` Module](#-the-os-module)
- [The `shutil` Module](#-the-shutil-module)
- [The `json` Module](#-the-json-module)
- [The `csv` Module](#-the-csv-module)
- [The `datetime` Module](#-the-datetime-module)
- [The `time` Module](#-the-time-module)
- [The `re` Module (Regular Expressions)](#-the-re-module-regular-expressions)
- [Common Errors](#-common-errors)
- [Best Practices](#-best-practices)
- [Summary](#-summary)
- [Practice Exercises](#-practice-exercises)

---

# 📖 Introduction to the Standard Library

Python's **Standard Library** is a vast collection of modules and packages that come pre-installed with Python.

These modules help developers perform tasks such as:

- Mathematical calculations
- Working with files
- Handling JSON and CSV data
- Managing directories
- Working with dates and time
- Generating random values
- Pattern matching using Regular Expressions

> **Note:** Since these modules are built into Python, they do not require installation using `pip`.

[⬆ Back to Top](#-table-of-contents)

---

# 📦 The `array` Module

The `array` module provides a space-efficient way to store arrays of similar data types.

```python
import array

arr = array.array('i', [1, 2, 3, 4])

print(arr)
```

Output

```
array('i', [1, 2, 3, 4])
```

Here,

- `'i'` represents an integer array.

[⬆ Back to Top](#-table-of-contents)

---

# ➗ The `math` Module

The `math` module provides mathematical functions.

```python
import math

print(math.sqrt(16))
```

Output

```
4.0
```

Other useful functions include:

```python
print(math.pi)

print(math.factorial(5))

print(math.ceil(3.2))

print(math.floor(3.8))
```

[⬆ Back to Top](#-table-of-contents)

---

# 🎲 The `random` Module

The `random` module generates random values.

```python
import random

print(random.randint(1, 10))
```

Output

```
7
```

> **Note:** `randint()` returns a random integer between the given range (inclusive).

Choose a random item.

```python
print(random.choice(["apple", "banana", "cherry"]))
```

Example Output

```
banana
```

[⬆ Back to Top](#-table-of-contents)

---

# 📂 The `os` Module

The `os` module provides functions to interact with the operating system.

Current working directory

```python
import os

print(os.getcwd())
```

Create a new directory

```python
os.mkdir("test_dir")
```

Other useful functions

```python
os.listdir()

os.remove("sample.txt")

os.rmdir("test_dir")
```

[⬆ Back to Top](#-table-of-contents)

---

# 📁 The `shutil` Module

The `shutil` module performs high-level file operations.

Copy a file

```python
import shutil

shutil.copyfile("source.txt", "destination.txt")
```

Other useful functions

```python
shutil.move()

shutil.copytree()

shutil.rmtree()
```

[⬆ Back to Top](#-table-of-contents)

---

# 🌐 The `json` Module

JSON is widely used for storing and exchanging data.

## Convert Dictionary to JSON

```python
import json

data = {
    "name": "Prav",
    "age": 25
}

json_str = json.dumps(data)

print(json_str)

print(type(json_str))
```

Output

```
{"name": "Prav", "age": 25}

<class 'str'>
```

---

## Convert JSON to Dictionary

```python
parsed_data = json.loads(json_str)

print(parsed_data)

print(type(parsed_data))
```

Output

```
{'name': 'Prav', 'age': 25}

<class 'dict'>
```

[⬆ Back to Top](#-table-of-contents)

---

# 📄 The `csv` Module

The `csv` module helps read and write CSV files.

## Writing to a CSV File

```python
import csv

with open("example.csv", mode="w", newline="") as file:

    writer = csv.writer(file)

    writer.writerow(["Name", "Age"])

    writer.writerow(["Prav", 32])
```

---

## Reading a CSV File

```python
with open("example.csv", mode="r") as file:

    reader = csv.reader(file)

    for row in reader:
        print(row)
```

Output

```
['Name', 'Age']

['Prav', '32']
```

[⬆ Back to Top](#-table-of-contents)

---

# 📅 The `datetime` Module

The `datetime` module works with dates and time.

```python
from datetime import datetime, timedelta

current_date = datetime.now()

print(current_date)
```

Yesterday's date

```python
yesterday = current_date - timedelta(days=1)

print(yesterday)
```

Tomorrow's date

```python
tomorrow = current_date + timedelta(days=1)

print(tomorrow)
```

[⬆ Back to Top](#-table-of-contents)

---

# ⏱️ The `time` Module

The `time` module provides time-related functions.

```python
import time

print(time.time())
```

Pause execution

```python
time.sleep(2)

print("Program Resumed")
```

> `sleep(2)` pauses the program for **2 seconds**.

[⬆ Back to Top](#-table-of-contents)

---

# 🔍 The `re` Module (Regular Expressions)

The `re` module is used for searching and matching patterns in text.

```python
import re

pattern = r"\d+"

text = "There are 123 apples and 456 oranges."

match = re.search(pattern, text)

print(match.group())
```

Output

```
123
```

Find all numbers

```python
numbers = re.findall(pattern, text)

print(numbers)
```

Output

```
['123', '456']
```

[⬆ Back to Top](#-table-of-contents)

---

# ❌ Common Errors

### Using `json.dump()` Instead of `json.dumps()`

Incorrect

```python
json.dump(data)
```

Correct

```python
json.dumps(data)
```

---

### Forgetting to Import a Module

```python
print(math.sqrt(16))
```

Raises

```
NameError
```

Correct

```python
import math
```

---

### Incorrect CSV Writer Variable

Incorrect

```python
write.writerow(...)
```

Correct

```python
writer.writerow(...)
```

---

### Incorrect Variable Name

Incorrect

```python
yesterday = now - timedelta(days=1)
```

Correct

```python
yesterday = current_date - timedelta(days=1)
```

[⬆ Back to Top](#-table-of-contents)

---

# ✅ Best Practices

- Import only the modules you need.
- Use aliases when appropriate (e.g., `import numpy as np`).
- Use `with open()` for file handling.
- Use `json.dumps()` and `json.loads()` correctly.
- Close files automatically using context managers.
- Use descriptive variable names.

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Summary

In this chapter, you learned:

- ✅ `array`
- ✅ `math`
- ✅ `random`
- ✅ `os`
- ✅ `shutil`
- ✅ `json`
- ✅ `csv`
- ✅ `datetime`
- ✅ `time`
- ✅ `re` (Regular Expressions)
- ✅ Common errors
- ✅ Best practices

Python's Standard Library provides powerful built-in modules that make development faster and more efficient.

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Practice Exercises

### Exercise 1

Create an integer array using the `array` module.

---

### Exercise 2

Generate five random numbers between 1 and 100.

---

### Exercise 3

Convert a dictionary into a JSON string and back into a dictionary.

---

### Exercise 4

Create and read a CSV file containing student information.

---

### Exercise 5

Use the `re` module to extract all email addresses from a text string.

---

### Exercise 6

Print today's date and the date seven days from today.

---

## 🎯 What's Next?

In **Day 12**, you'll learn about **File Handling in Python**, including:

- 📂 Opening Files
- 📖 Reading Files
- ✍️ Writing Files
- ➕ Appending Data
- ⚠️ Exception Handling
- 🌍 Real-world File Operations

Happy Coding! 🚀