# 📘 Day 03: Operators in Python

> Operators are special symbols used to perform operations on variables and values. They are essential for performing calculations, comparisons, and logical decisions in Python.

---

## 📑 Table of Contents

- [Introduction to Operators](#-introduction-to-operators)
- [Arithmetic Operators](#-arithmetic-operators)
  - [Addition (+)](#addition-)
  - [Subtraction (-)](#subtraction--)
  - [Multiplication (*)](#multiplication-)
  - [Division (/)](#division-)
  - [Floor Division (//)](#floor-division-)
  - [Modulus (%)](#modulus-)
  - [Exponentiation (**)](#exponentiation-)
- [Comparison Operators](#-comparison-operators)
- [Logical Operators](#-logical-operators)
- [Operator Precedence](#-operator-precedence)
- [Common Errors](#-common-errors)
- [Best Practices](#-best-practices)
- [Summary](#-summary)
- [Practice Exercises](#-practice-exercises)

---

![Operators](images/ChatGPT%20Image%20Jul%203,%202026,%2006_47_42%20PM.png)

---

# 📖 Introduction to Operators

Operators are symbols that tell Python to perform a specific operation on one or more operands.

Python provides several types of operators:

- Arithmetic Operators
- Comparison Operators
- Logical Operators

These operators are widely used in calculations, conditions, and decision-making.

[⬆ Back to Top](#-table-of-contents)

---

# ➕ Arithmetic Operators

Arithmetic operators perform mathematical calculations.

| Operator | Name | Example |
|----------|------|---------|
| `+` | Addition | `a + b` |
| `-` | Subtraction | `a - b` |
| `*` | Multiplication | `a * b` |
| `/` | Division | `a / b` |
| `//` | Floor Division | `a // b` |
| `%` | Modulus | `a % b` |
| `**` | Exponentiation | `a ** b` |

Example

```python
a = 15
b = 20

add_result = a + b
sub_result = b - a
multi_result = a * b
div_result = a / b
floor_div_result = a // b
modulus_result = a % b
exponent_result = a ** b

print("Addition:", add_result)
print("Subtraction:", sub_result)
print("Multiplication:", multi_result)
print("Division:", div_result)
print("Floor Division:", floor_div_result)
print("Modulus:", modulus_result)
print("Exponentiation:", exponent_result)
```

### Output

```
Addition: 35
Subtraction: 5
Multiplication: 300
Division: 0.75
Floor Division: 0
Modulus: 15
Exponentiation: 332842204964336809...
```

> **Note:** Floor division (`//`) returns the integer quotient by discarding the decimal part.

[⬆ Back to Top](#-table-of-contents)

---

## Addition (+)

Adds two operands.

```python
a = 10
b = 5

print(a + b)
```

Output

```
15
```

---

## Subtraction (-)

Subtracts one operand from another.

```python
print(20 - 8)
```

Output

```
12
```

---

## Multiplication (*)

Multiplies two numbers.

```python
print(6 * 7)
```

Output

```
42
```

---

## Division (/)

Returns the quotient as a floating-point number.

```python
print(20 / 5)
```

Output

```
4.0
```

---

## Floor Division (//)

Returns only the integer quotient.

```python
print(20 // 3)
```

Output

```
6
```

---

## Modulus (%)

Returns the remainder after division.

```python
print(20 % 3)
```

Output

```
2
```

---

## Exponentiation (**)

Raises the first operand to the power of the second.

```python
print(2 ** 5)
```

Output

```
32
```

[⬆ Back to Top](#-table-of-contents)

---

# ⚖️ Comparison Operators

Comparison operators compare two values and always return **True** or **False**.

| Operator | Description |
|----------|-------------|
| `==` | Equal to |
| `!=` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |

Example

```python
a = 10
b = 20

print(a == b)
print(a != b)
print(a > b)
print(a < b)
print(a >= b)
print(a <= b)
```

### Output

```
False
True
False
True
False
True
```

### Comparing Strings

```python
str1 = "prav"
str2 = "kosanam"

print(str1 == str2)
print(str1 != str2)
```

Output

```
False
True
```

[⬆ Back to Top](#-table-of-contents)

---

# 🔀 Logical Operators

Logical operators combine multiple conditions.

| Operator | Description |
|----------|-------------|
| `and` | Returns True if both conditions are True |
| `or` | Returns True if at least one condition is True |
| `not` | Reverses the Boolean value |

Example

```python
X = True
Y = False

result = X and Y
print(result)

result2 = X or Y
print(result2)

result3 = not X
print(result3)
```

### Output

```
False
True
False
```

### Truth Table

| X | Y | X and Y | X or Y | not X |
|---|---|----------|---------|-------|
| True | True | True | True | False |
| True | False | False | True | False |
| False | True | False | True | True |
| False | False | False | False | True |

[⬆ Back to Top](#-table-of-contents)

---

# 📌 Operator Precedence

Python follows operator precedence while evaluating expressions.

Highest precedence:

1. `()` Parentheses
2. `**` Exponentiation
3. `*`, `/`, `//`, `%`
4. `+`, `-`
5. Comparison Operators
6. `not`
7. `and`
8. `or`

Example

```python
result = 10 + 2 * 5

print(result)
```

Output

```
20
```

Using parentheses:

```python
result = (10 + 2) * 5

print(result)
```

Output

```
60
```

[⬆ Back to Top](#-table-of-contents)

---

# ❌ Common Errors

## 1. Division by Zero

```python
10 / 0
```

Raises:

```
ZeroDivisionError
```

---

## 2. Comparing Different Data Types

```python
10 > "20"
```

Raises:

```
TypeError
```

---

## 3. Incorrect Logical Expression

```python
True and
```

Raises a syntax error.

---

## 4. Using Assignment Instead of Comparison

Incorrect

```python
if a = 10:
```

Correct

```python
if a == 10:
```

[⬆ Back to Top](#-table-of-contents)

---

# ✅ Best Practices

- Use meaningful variable names.
- Use parentheses to improve readability.
- Avoid unnecessary complex expressions.
- Always check for division by zero.
- Use comparison operators carefully inside conditions.

Example

```python
if age >= 18 and is_verified:
    print("Access Granted")
```

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Summary

In this chapter, you learned:

- ✅ Arithmetic Operators
- ✅ Comparison Operators
- ✅ Logical Operators
- ✅ Operator Precedence
- ✅ Common Errors
- ✅ Best Practices

Operators are one of the most important concepts in Python because they are used in calculations, conditions, loops, and decision-making.

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Practice Exercises

### Exercise 1

Create two variables `a` and `b` and perform all arithmetic operations.

---

### Exercise 2

Compare two numbers using all comparison operators.

---

### Exercise 3

Write a program to check whether a number is even or odd using the modulus operator.

---

### Exercise 4

Create two Boolean variables and perform:

- AND
- OR
- NOT

---

### Exercise 5

Predict the output before running the following code:

```python
print(5 + 2 * 3)
print((5 + 2) * 3)
print(10 > 5 and 5 > 20)
```

---

## 🎯 What's Next?

In **Day 04**, you'll learn about:

- Conditional Statements (`if`, `elif`, `else`)
- Nested Conditions
- Match Statement
- Practical Decision-Making Examples

Happy Coding! 🚀
