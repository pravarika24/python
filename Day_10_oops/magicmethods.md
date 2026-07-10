# 📘 Day 10: Magic Methods (Dunder Methods) in Python

> Magic methods, also known as **Dunder (Double Underscore) Methods**, are special methods in Python that begin and end with double underscores (`__`). They allow developers to customize the behavior of objects for built-in operations such as printing, comparisons, arithmetic operations, indexing, iteration, and much more.

---

## 📑 Table of Contents

- [Introduction to Magic Methods](#-introduction-to-magic-methods)
- [What are Magic Methods?](#-what-are-magic-methods)
- [Common Magic Methods](#-common-magic-methods)
- [Exploring Magic Methods using `dir()`](#-exploring-magic-methods-using-dir)
- [The `__init__()` Method](#-the-__init__-method)
- [The `__str__()` Method](#-the-__str__-method)
- [The `__repr__()` Method](#-the-__repr__-method)
- [Difference Between `__str__()` and `__repr__()`](#-difference-between-__str__-and-__repr__)
- [Common Errors](#-common-errors)
- [Best Practices](#-best-practices)
- [Summary](#-summary)
- [Practice Exercises](#-practice-exercises)

---

# 📖 Introduction to Magic Methods

Magic methods are predefined methods in Python that allow classes to interact with Python's built-in syntax and functions.

They are called automatically whenever certain operations are performed on an object.

For example,

- Creating an object
- Printing an object
- Comparing objects
- Using arithmetic operators
- Accessing list-like elements

These methods make custom classes behave like Python's built-in objects.

[⬆ Back to Top](#-table-of-contents)

---

# ✨ What are Magic Methods?

Magic methods are special methods whose names begin and end with double underscores (`__`).

Some commonly used magic methods include:

| Magic Method | Purpose |
|--------------|---------|
| `__init__()` | Initializes an object |
| `__str__()` | Returns a user-friendly string representation |
| `__repr__()` | Returns the official string representation |
| `__len__()` | Returns the length of an object |
| `__getitem__()` | Retrieves an item using indexing |
| `__setitem__()` | Assigns a value using indexing |

Python automatically calls these methods when required.

[⬆ Back to Top](#-table-of-contents)

---

# 📋 Common Magic Methods

### `__init__()`

Called automatically when an object is created.

---

### `__str__()`

Defines how an object is displayed using `print()`.

---

### `__repr__()`

Returns an official representation of the object, mainly used for debugging.

---

### `__len__()`

Returns the length of an object.

Example:

```python
len(my_object)
```

---

### `__getitem__()`

Allows indexing.

```python
obj[0]
```

---

### `__setitem__()`

Allows assigning values using indexing.

```python
obj[0] = value
```

[⬆ Back to Top](#-table-of-contents)

---

# 🔍 Exploring Magic Methods using `dir()`

Every Python object contains many built-in magic methods.

```python
class Person:
    pass

person = Person()

print(dir(person))
```

Output (Partial)

```
[
'__class__',
'__delattr__',
'__dict__',
'__doc__',
'__eq__',
'__init__',
'__repr__',
'__str__',
...
]
```

The `dir()` function lists all available attributes and methods of an object.

[⬆ Back to Top](#-table-of-contents)

---

# 🚀 The `__init__()` Method

`__init__()` is called automatically whenever an object is created.

```python
class Person:

    def __init__(self, name, age):

        self.name = name

        self.age = age
```

Create an object.

```python
person = Person("Prav", 27)
```

The constructor initializes the object's attributes.

[⬆ Back to Top](#-table-of-contents)

---

# 🖨️ The `__str__()` Method

Without overriding `__str__()`, printing an object displays its memory address.

Example

```python
class Person:

    def __init__(self, name, age):

        self.name = name

        self.age = age
```

```python
person = Person("Prav", 27)

print(person)
```

Output

```
<__main__.Person object at 0x...>
```

Now override `__str__()`.

```python
class Person:

    def __init__(self, name, age):

        self.name = name

        self.age = age

    def __str__(self):

        return f"{self.name}, {self.age} years old"
```

```python
person = Person("Prav", 27)

print(person)
```

Output

```
Prav, 27 years old
```

> **Note:** `__str__()` is intended for end users and should return a readable description.

[⬆ Back to Top](#-table-of-contents)

---

# 🛠️ The `__repr__()` Method

`__repr__()` returns the official string representation of an object.

It is mainly used for debugging.

```python
class Person:

    def __init__(self, name, age):

        self.name = name

        self.age = age

    def __repr__(self):

        return f"Person(name='{self.name}', age={self.age})"
```

```python
person = Person("Prav", 27)

print(repr(person))
```

Output

```
Person(name='Prav', age=27)
```

[⬆ Back to Top](#-table-of-contents)

---

# ⚖️ Difference Between `__str__()` and `__repr__()`

```python
class Person:

    def __init__(self, name, age):

        self.name = name

        self.age = age

    def __str__(self):

        return f"{self.name}, {self.age} years old"

    def __repr__(self):

        return f"Person(name='{self.name}', age={self.age})"
```

```python
person = Person("Prav", 27)

print(person)

print(repr(person))
```

Output

```
Prav, 27 years old

Person(name='Prav', age=27)
```

### Difference

| `__str__()` | `__repr__()` |
|-------------|--------------|
| User-friendly | Developer-friendly |
| Used by `print()` | Used by `repr()` |
| Readable output | Detailed representation |
| Intended for users | Intended for debugging |

[⬆ Back to Top](#-table-of-contents)

---

# 🌍 Real-World Example

```python
class Book:

    def __init__(self, title, author):

        self.title = title

        self.author = author

    def __str__(self):

        return f"{self.title} by {self.author}"

    def __repr__(self):

        return f"Book(title='{self.title}', author='{self.author}')"
```

```python
book = Book("Python Basics", "John Smith")

print(book)

print(repr(book))
```

Output

```
Python Basics by John Smith

Book(title='Python Basics', author='John Smith')
```

[⬆ Back to Top](#-table-of-contents)

---

# ❌ Common Errors

## Forgetting to Return a String

Incorrect

```python
def __str__(self):

    print(self.name)
```

Correct

```python
def __str__(self):

    return self.name
```

---

## Misspelling Magic Methods

Incorrect

```python
__init
```

Correct

```python
__init__
```

---

## Returning Non-String Values

Incorrect

```python
def __repr__(self):

    return 10
```

Raises

```
TypeError
```

Always return a string.

[⬆ Back to Top](#-table-of-contents)

---

# ✅ Best Practices

- Always override `__str__()` for user-friendly output.
- Override `__repr__()` for debugging.
- Keep string representations simple and meaningful.
- Return strings from both methods.
- Use descriptive class and attribute names.

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Summary

In this chapter, you learned:

- ✅ What Magic Methods are
- ✅ `__init__()`
- ✅ `__str__()`
- ✅ `__repr__()`
- ✅ `__len__()`
- ✅ `__getitem__()`
- ✅ `__setitem__()`
- ✅ Difference between `__str__()` and `__repr__()`
- ✅ Common mistakes
- ✅ Best practices

Magic methods allow custom classes to integrate seamlessly with Python's built-in functionality, making code cleaner, more intuitive, and easier to use.

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Practice Exercises

### Exercise 1

Create a `Student` class and override `__str__()`.

---

### Exercise 2

Override `__repr__()` in the `Student` class.

---

### Exercise 3

Create a `Book` class that displays different outputs using `print()` and `repr()`.

---

### Exercise 4

Create a `ShoppingCart` class and override `__len__()` to return the number of items.

---

### Exercise 5

Create a custom container class and implement:

- `__getitem__()`
- `__setitem__()`

---

## 🎯 What's Next?

In upcoming lessons, you'll learn about **Iterators and Generators in Python**, including:

- 🔄 Iterators
- ⚡ The `iter()` Function
- ▶️ The `next()` Function
- 🌱 Generators
- 📝 The `yield` Keyword
- 🌍 Practical Examples

Happy Coding! 🚀