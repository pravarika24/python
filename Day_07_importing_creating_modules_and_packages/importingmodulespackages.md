# 📘 Day 07: Modules and Packages in Python

> Modules and packages help organize Python programs into reusable components. They make code cleaner, modular, and easier to maintain.

---

## 📑 Table of Contents

- [Introduction to Modules and Packages](#-introduction-to-modules-and-packages)
- [What is a Module?](#-what-is-a-module)
- [Importing Modules](#-importing-modules)
- [Importing Specific Functions](#-importing-specific-functions)
- [Using Aliases](#-using-aliases)
- [Importing All Functions](#-importing-all-functions)
- [Creating Custom Packages](#-creating-custom-packages)
- [Importing Custom Modules](#-importing-custom-modules)
- [Package Structure](#-package-structure)
- [Common Errors](#-common-errors)
- [Best Practices](#-best-practices)
- [Summary](#-summary)
- [Practice Exercises](#-practice-exercises)

---

![Modules and Packages in Python](images/ChatGPT%20Image%20Jul%209,%202026,%2004_42_50%20PM.png)

---

# 📖 Introduction to Modules and Packages

As programs become larger, writing everything in a single file becomes difficult to manage.

Python provides **Modules** and **Packages** to organize code into smaller, reusable files.

### Benefits

- Reusable code
- Better organization
- Easier maintenance
- Improves readability
- Encourages modular programming

[⬆ Back to Top](#-table-of-contents)

---

# 📦 What is a Module?

A **module** is simply a Python file (`.py`) containing variables, functions, and classes.

Python provides many built-in modules such as:

- `math`
- `random`
- `datetime`
- `os`
- `sys`

Example

```python
import math
```

Now we can access all functions inside the `math` module.

```python
print(math.sqrt(16))
```

Output

```
4.0
```

[⬆ Back to Top](#-table-of-contents)

---

# 📥 Importing Modules

Import an entire module.

```python
import math

print(math.sqrt(16))
```

Output

```
4.0
```

Another example

```python
import numpy
```

Create a NumPy array.

```python
arr = numpy.array([1,2,3,4,5])

print(arr)
```

[⬆ Back to Top](#-table-of-contents)

---

# 🎯 Importing Specific Functions

Instead of importing the whole module, import only the required functions.

```python
from math import sqrt, pi
```

Now they can be used directly.

```python
print(sqrt(16))

print(pi)
```

Output

```
4.0

3.141592653589793
```

This makes the code shorter.

[⬆ Back to Top](#-table-of-contents)

---

# 🏷️ Using Aliases

Aliases provide shorter names for modules.

```python
import numpy as np
```

Example

```python
numbers = np.array([1,2,3,4,5])

print(numbers)
```

Output

```
[1 2 3 4 5]
```

Another common alias

```python
import pandas as pd
```

[⬆ Back to Top](#-table-of-contents)

---

# ⭐ Importing All Functions

You can import every function from a module.

```python
from math import *
```

Example

```python
print(sqrt(16))

print(pi)
```

Output

```
4.0

3.141592653589793
```

> **Note:** Although possible, importing everything using `*` is **not recommended** because it can lead to namespace conflicts.

[⬆ Back to Top](#-table-of-contents)

---

# 🛠️ Creating Custom Packages

A **package** is a collection of related modules organized inside a directory.

Example folder structure

```
package/
│
├── __init__.py
├── maths.py
│
└── subpackages/
    ├── __init__.py
    └── mult.py
```

### maths.py

```python
def addition(a, b):
    return a + b
```

### mult.py

```python
def multiply(a, b):
    return a * b
```

[⬆ Back to Top](#-table-of-contents)

---

# 📂 Importing Custom Modules

### Import a Specific Function

```python
from package.maths import addition

print(addition(2,3))
```

Output

```
5
```

---

### Import the Entire Module

```python
from package import maths

print(maths.addition(2,3))
```

Output

```
5
```

---

### Import Everything

```python
from package.maths import *

print(addition(2,3))
```

Output

```
5
```

---

### Import from a Subpackage

```python
from package.subpackages.mult import multiply

print(multiply(4,5))
```

Output

```
20
```

[⬆ Back to Top](#-table-of-contents)

---

# 📁 Package Structure

Example

```
project/

│── main.py

│
└── package/

    ├── __init__.py

    ├── maths.py

    │
    └── subpackages/

        ├── __init__.py

        └── mult.py
```

Here,

- `main.py` imports functions from the package.
- `__init__.py` tells Python that the directory should be treated as a package.

[⬆ Back to Top](#-table-of-contents)

---

# ❌ Common Errors

## Module Not Found

```python
import maths
```

Raises

```
ModuleNotFoundError
```

when the module does not exist.

---

## Misspelled Module Name

Incorrect

```python
import mat
```

Correct

```python
import math
```

---

## Using Functions Without Importing

Incorrect

```python
print(sqrt(16))
```

Raises

```
NameError
```

Correct

```python
from math import sqrt

print(sqrt(16))
```

---

## Using `import *`

Although valid,

```python
from math import *
```

is discouraged because multiple modules may contain functions with the same name.

[⬆ Back to Top](#-table-of-contents)

---

# ✅ Best Practices

- Import only what you need.
- Use aliases for long module names.
- Avoid `from module import *`.
- Organize large projects into packages.
- Give modules meaningful names.
- Keep related functions together in the same module.

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Summary

In this chapter, you learned:

- ✅ What modules are
- ✅ What packages are
- ✅ Importing modules
- ✅ Importing specific functions
- ✅ Using aliases
- ✅ Importing all functions
- ✅ Creating custom packages
- ✅ Importing custom modules
- ✅ Package structure
- ✅ Common errors
- ✅ Best practices

Modules and packages make Python applications modular, reusable, and easier to maintain.

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Practice Exercises

### Exercise 1

Import the `math` module and calculate the square root of **81**.

---

### Exercise 2

Import only the `factorial()` function from the `math` module.

---

### Exercise 3

Import NumPy using the alias `np` and create a NumPy array.

---

### Exercise 4

Create a custom module named `calculator.py` with functions for:

- Addition
- Subtraction
- Multiplication
- Division

Import and use these functions.

---

### Exercise 5

Create a package named `geometry` containing:

- `circle.py`
- `rectangle.py`

Write functions to calculate area and perimeter.

---

## 🎯 What's Next?

In **Day 08**, you'll learn about **File Handling in Python**, including:

- 📂 Opening Files
- ✍️ Reading Files
- 📝 Writing Files
- ➕ Appending Data
- ❌ Handling File Exceptions
- 🌍 Practical Examples

Happy Coding! 🚀