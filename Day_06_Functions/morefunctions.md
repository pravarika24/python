# 📘 Day 06 - Part 02: Practical Function Examples

> In this chapter, we'll apply Python functions to solve real-world problems such as temperature conversion, password validation, shopping cart calculations, palindrome checking, and recursion.

---

## 📑 Table of Contents

- [Temperature Conversion](#-temperature-conversion)
- [Password Strength Checker](#-password-strength-checker)
- [Shopping Cart Total Cost Calculator](#-shopping-cart-total-cost-calculator)
- [Palindrome Checker](#-palindrome-checker)
- [Factorial Using Recursion](#-factorial-using-recursion)
- [Common Errors](#-common-errors)
- [Best Practices](#-best-practices)
- [Summary](#-summary)
- [Practice Exercises](#-practice-exercises)

---

# 🌡️ Temperature Conversion

This function converts temperatures between **Celsius** and **Fahrenheit**.

## Formula

- Celsius → Fahrenheit

```
°F = (°C × 9/5) + 32
```

- Fahrenheit → Celsius

```
°C = (°F − 32) × 5/9
```

### Example

```python
def temp_conv(temp, unit):
    """
    Convert temperature between Celsius and Fahrenheit.
    """

    if unit.upper() == "C":
        return temp * (9 / 5) + 32

    elif unit.upper() == "F":
        return (temp - 32) * 5 / 9

    else:
        return "Invalid Unit"
```

### Calling the Function

```python
print(temp_conv(25, "C"))

print(temp_conv(75, "F"))
```

### Output

```
77.0

23.88888888888889
```

[⬆ Back to Top](#-table-of-contents)

---

# 🔐 Password Strength Checker

A strong password should have:

- Minimum 8 characters
- At least one uppercase letter
- At least one lowercase letter
- At least one digit
- At least one special character

### Example

```python
def pass_checker(password):
    """
    Checks whether a password is strong.
    """

    if len(password) < 8:
        return False

    if not any(char.isdigit() for char in password):
        return False

    if not any(char.islower() for char in password):
        return False

    if not any(char.isupper() for char in password):
        return False

    if not any(char in "!@#$%^&*()" for char in password):
        return False

    return True
```

### Calling the Function

```python
print(pass_checker("WeakPwd"))

print(pass_checker("Strong@123"))
```

### Output

```
False

True
```

[⬆ Back to Top](#-table-of-contents)

---

# 🛒 Shopping Cart Total Cost Calculator

This function calculates the total price of items in a shopping cart.

### Example

```python
def calculate_cost(cart):

    total_cost = 0

    for item in cart:
        total_cost += item["price"] * item["quantity"]

    return total_cost
```

### Shopping Cart

```python
cart = [
    {"name": "Apple", "price": 0.5, "quantity": 4},
    {"name": "Banana", "price": 0.3, "quantity": 5},
    {"name": "Orange", "price": 0.7, "quantity": 6}
]
```

### Calling the Function

```python
print(calculate_cost(cart))
```

### Output

```
7.699999999999999
```

[⬆ Back to Top](#-table-of-contents)

---

# 🔁 Palindrome Checker

A palindrome is a word or sentence that reads the same forwards and backwards.

Examples

```
madam

racecar

level
```

### Example

```python
def is_palindrome(text):

    text = text.lower().replace(" ", "")

    return text == text[::-1]
```

### Calling the Function

```python
print(is_palindrome("Madam"))

print(is_palindrome("Python"))
```

### Output

```
True

False
```

[⬆ Back to Top](#-table-of-contents)

---

# 🔄 Factorial Using Recursion

Recursion is a technique where a function calls itself.

The factorial of a number is

```
5! = 5 × 4 × 3 × 2 × 1
```

### Example

```python
def factorial(n):

    if n == 0 or n == 1:
        return 1

    return n * factorial(n - 1)
```

### Calling the Function

```python
print(factorial(5))
```

### Output

```
120
```

[⬆ Back to Top](#-table-of-contents)

---

# ❌ Common Errors

## Forgetting the Base Case in Recursion

Incorrect

```python
def factorial(n):

    return n * factorial(n - 1)
```

This causes

```
RecursionError
```

---

## Using `false` Instead of `False`

Incorrect

```python
return false
```

Correct

```python
return False
```

---

## Dictionary Key Errors

Incorrect

```python
item["cost"]
```

If `"cost"` does not exist, Python raises a

```
KeyError
```

---

## Misspelled Variable Names

Incorrect

```python
tota_cost
```

Correct

```python
total_cost
```

[⬆ Back to Top](#-table-of-contents)

---

# ✅ Best Practices

- Keep each function focused on one task.
- Write descriptive function names.
- Use docstrings.
- Validate user input.
- Always return meaningful values.
- Handle invalid input gracefully.
- Keep recursive functions simple and include a base case.

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Summary

In this chapter, you learned how to solve practical problems using functions.

Topics covered:

- ✅ Temperature Conversion
- ✅ Password Strength Checker
- ✅ Shopping Cart Calculator
- ✅ Palindrome Checker
- ✅ Factorial Using Recursion
- ✅ Common Errors
- ✅ Best Practices

These examples demonstrate how functions can be used to build reusable and maintainable programs.

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Practice Exercises

### Exercise 1

Write a function to convert kilometers to miles.

---

### Exercise 2

Write a function to validate an email address.

---

### Exercise 3

Write a function that calculates the average marks of a student.

---

### Exercise 4

Write a recursive function to calculate Fibonacci numbers.

---

### Exercise 5

Create a shopping cart program that calculates:

- Total Cost
- Total Quantity
- Average Price

---

## 🎯 What's Next?

In **Day 07**, you'll learn about:

- 🧩 Lambda Functions
- 🔄 `map()`
- 🎯 `filter()`
- 📝 Anonymous Functions
- 🌍 Real-world Examples

Happy Coding! 🚀