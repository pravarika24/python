# 📘 Day 10: Operator Overloading in Python

> Operator Overloading allows developers to define how operators such as `+`, `-`, `*`, `/`, and comparison operators behave when used with custom objects. This is achieved by overriding Python's **magic methods** (also called **dunder methods**).

---

## 📑 Table of Contents

- [Introduction to Operator Overloading](#-introduction-to-operator-overloading)
- [What are Magic Methods?](#-what-are-magic-methods)
- [Common Operator Overloading Methods](#-common-operator-overloading-methods)
- [Creating a Vector Class](#-creating-a-vector-class)
- [Overloading the `+` Operator](#-overloading-the--operator)
- [Overloading the `-` Operator](#-overloading-the---operator)
- [Overloading the `*` Operator](#-overloading-the--operator-1)
- [Using `__repr__()`](#-using-__repr__)
- [Complete Example](#-complete-example)
- [Common Errors](#-common-errors)
- [Best Practices](#-best-practices)
- [Summary](#-summary)
- [Practice Exercises](#-practice-exercises)

---

# 📖 Introduction to Operator Overloading

Python allows built-in operators like:

- `+`
- `-`
- `*`
- `/`
- `==`
- `<`

to work with user-defined objects.

This feature is called **Operator Overloading**.

It is implemented by overriding **magic methods** (also known as **dunder methods**).

Example:

Instead of writing

```python
vector1.add(vector2)
```

we can simply write

```python
vector1 + vector2
```

[⬆ Back to Top](#-table-of-contents)

---

# ✨ What are Magic Methods?

Magic methods are special methods surrounded by double underscores.

Examples

```python
__init__()

__str__()

__repr__()

__add__()

__sub__()

__mul__()

__len__()
```

Python automatically calls these methods when corresponding operators are used.

[⬆ Back to Top](#-table-of-contents)

---

# ⚙️ Common Operator Overloading Methods

| Magic Method | Operator | Description |
|--------------|----------|-------------|
| `__add__(self, other)` | `+` | Adds two objects |
| `__sub__(self, other)` | `-` | Subtracts two objects |
| `__mul__(self, other)` | `*` | Multiplies two objects |
| `__truediv__(self, other)` | `/` | Divides two objects |
| `__eq__(self, other)` | `==` | Checks equality |
| `__lt__(self, other)` | `<` | Less than comparison |
| `__gt__(self, other)` | `>` | Greater than comparison |

[⬆ Back to Top](#-table-of-contents)

---

# 🧩 Creating a Vector Class

Let's create a custom `Vector` class.

```python
class Vector:

    def __init__(self, x, y):

        self.x = x

        self.y = y
```

This class stores two coordinates.

[⬆ Back to Top](#-table-of-contents)

---

# ➕ Overloading the `+` Operator

Override the `__add__()` method.

```python
class Vector:

    def __init__(self, x, y):

        self.x = x

        self.y = y

    def __add__(self, other):

        return Vector(
            self.x + other.x,
            self.y + other.y
        )
```

Example

```python
v1 = Vector(2, 3)

v2 = Vector(4, 5)

print(v1 + v2)
```

Output

```
Vector(6, 8)
```

[⬆ Back to Top](#-table-of-contents)

---

# ➖ Overloading the `-` Operator

```python
def __sub__(self, other):

    return Vector(
        self.x - other.x,
        self.y - other.y
    )
```

Example

```python
print(v1 - v2)
```

Output

```
Vector(-2, -2)
```

[⬆ Back to Top](#-table-of-contents)

---

# ✖️ Overloading the `*` Operator

```python
def __mul__(self, other):

    return Vector(
        self.x * other.x,
        self.y * other.y
    )
```

Example

```python
print(v1 * v2)
```

Output

```
Vector(8, 15)
```

[⬆ Back to Top](#-table-of-contents)

---

# 🖨️ Using `__repr__()`

Without `__repr__()`, printing an object displays its memory address.

```python
print(v1)
```

Output

```
<__main__.Vector object at 0x...>
```

Override `__repr__()`.

```python
def __repr__(self):

    return f"Vector({self.x}, {self.y})"
```

Now

```python
print(v1)
```

Output

```
Vector(2, 3)
```

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Complete Example

```python
class Vector:

    def __init__(self, x, y):

        self.x = x
        self.y = y

    def __add__(self, other):

        return Vector(
            self.x + other.x,
            self.y + other.y
        )

    def __sub__(self, other):

        return Vector(
            self.x - other.x,
            self.y - other.y
        )

    def __mul__(self, other):

        return Vector(
            self.x * other.x,
            self.y * other.y
        )

    def __repr__(self):

        return f"Vector({self.x}, {self.y})"
```

Create objects.

```python
v1 = Vector(2, 3)

v2 = Vector(4, 5)
```

Perform operations.

```python
print(v1 + v2)

print(v1 - v2)

print(v1 * v2)
```

Output

```
Vector(6, 8)

Vector(-2, -2)

Vector(8, 15)
```

[⬆ Back to Top](#-table-of-contents)

---

# 🌍 Real-World Example

Suppose we have a `Money` class.

```python
class Money:

    def __init__(self, amount):

        self.amount = amount

    def __add__(self, other):

        return Money(self.amount + other.amount)

    def __repr__(self):

        return f"${self.amount}"
```

Example

```python
wallet1 = Money(150)

wallet2 = Money(250)

print(wallet1 + wallet2)
```

Output

```
$400
```

Operator overloading makes custom objects behave like built-in types.

[⬆ Back to Top](#-table-of-contents)

---

# ❌ Common Errors

## Forgetting `__repr__()`

```python
print(v1)
```

Output

```
<__main__.Vector object at ...>
```

Always override `__repr__()` for readable output.

---

## Returning the Wrong Type

Incorrect

```python
return self.x + other.x
```

Correct

```python
return Vector(
    self.x + other.x,
    self.y + other.y
)
```

---

## Operating on Different Types

```python
v1 + 10
```

Raises

```
AttributeError
```

unless additional type checking is implemented.

[⬆ Back to Top](#-table-of-contents)

---

# ✅ Best Practices

- Overload operators only when they make logical sense.
- Return objects of the same class.
- Implement `__repr__()` for better debugging.
- Keep overloaded methods simple and intuitive.
- Add type checking when working with different object types.

Example

```python
if not isinstance(other, Vector):
    return NotImplemented
```

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Summary

In this chapter, you learned:

- ✅ What Operator Overloading is
- ✅ Magic Methods (Dunder Methods)
- ✅ `__add__()`
- ✅ `__sub__()`
- ✅ `__mul__()`
- ✅ `__repr__()`
- ✅ Real-world examples
- ✅ Common mistakes
- ✅ Best practices

Operator overloading allows custom classes to behave like Python's built-in data types, making code more intuitive and expressive.

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Practice Exercises

### Exercise 1

Create a `Point` class and overload the `+` operator.

---

### Exercise 2

Create a `ComplexNumber` class and overload:

- `+`
- `-`
- `*`

---

### Exercise 3

Create a `Book` class and overload the `==` operator to compare books by ISBN.

---

### Exercise 4

Create a `Student` class and overload the `<` operator to compare marks.

---

### Exercise 5

Create a `BankAccount` class and overload the `+` operator to combine account balances.

---

## 🎯 What's Next?

In upcoming lessons, you'll learn about **Duck Typing and Special (Magic) Methods in Python**, including:

- 🦆 Duck Typing
- ✨ `__str__()`
- 📏 `__len__()`
- 🔄 `__iter__()`
- 🌍 Practical Examples

Happy Coding! 🚀