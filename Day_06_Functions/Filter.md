# 📘 Day 09: The `filter()` Function in Python

> The `filter()` function is a built-in Python function used to filter elements from an iterable based on a condition. It returns an iterator containing only the elements for which the given function returns `True`.

---

## 📑 Table of Contents

- [Introduction to `filter()`](#-introduction-to-filter)
- [Syntax](#-syntax)
- [Using `filter()` with a Regular Function](#-using-filter-with-a-regular-function)
- [Using `filter()` with Lambda Functions](#-using-filter-with-lambda-functions)
- [Filtering with Multiple Conditions](#-filtering-with-multiple-conditions)
- [Using `filter()` with Dictionaries](#-using-filter-with-dictionaries)
- [Practical Examples](#-practical-examples)
- [Common Errors](#-common-errors)
- [Best Practices](#-best-practices)
- [Summary](#-summary)
- [Practice Exercises](#-practice-exercises)

---

![map() and filter() in Python](images/mapandfilter.png)

---

# 📖 Introduction to `filter()`

The **`filter()`** function constructs an iterator from the elements of an iterable for which a given function returns **`True`**.

It is commonly used to filter data based on a condition without writing explicit loops.

### Benefits

- Produces cleaner code
- Improves readability
- Works efficiently with iterables
- Commonly used with lambda functions

[⬆ Back to Top](#-table-of-contents)

---

# ✍️ Syntax

```python
filter(function, iterable)
```

- **function** → Returns `True` or `False`
- **iterable** → List, tuple, set, etc.

> **Note:** `filter()` returns a filter object (iterator). Convert it into a list using `list()` to view the results.

[⬆ Back to Top](#-table-of-contents)

---

# 🔄 Using `filter()` with a Regular Function

Create a function to check whether a number is even.

```python
def even(num):

    return num % 2 == 0
```

Test the function.

```python
print(even(20))
```

Output

```
True
```

Apply it to a list.

```python
numbers = [1,2,3,4,5,6,7,8,9,10,11,12]

result = list(filter(even, numbers))

print(result)
```

Output

```
[2, 4, 6, 8, 10, 12]
```

[⬆ Back to Top](#-table-of-contents)

---

# ⚡ Using `filter()` with Lambda Functions

Instead of defining a separate function, we can use a lambda function.

```python
numbers = [1,2,3,4,5,6,7,8,9]

greater_than_five = list(
    filter(lambda x: x > 5, numbers)
)

print(greater_than_five)
```

Output

```
[6, 7, 8, 9]
```

Lambda functions make the code shorter and more readable.

[⬆ Back to Top](#-table-of-contents)

---

# 🔀 Filtering with Multiple Conditions

Multiple conditions can be combined using logical operators.

```python
numbers = [1,2,3,4,5,6,7,8,9]

even_and_greater = list(
    filter(lambda x: x > 5 and x % 2 == 0, numbers)
)

print(even_and_greater)
```

Output

```
[6, 8]
```

Here,

- Number must be greater than 5
- Number must be even

Both conditions must be true.

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Using `filter()` with Dictionaries

`filter()` can also be used with lists of dictionaries.

```python
people = [
    {"name": "Prav", "age": 27},
    {"name": "Kosa", "age": 28},
    {"name": "John", "age": 25}
]
```

Create a function.

```python
def age_greater(person):
    return person["age"] > 25
```

Apply the filter.

```python
result = list(filter(age_greater, people))

print(result)
```

Output

```
[
 {'name': 'Prav', 'age': 27},
 {'name': 'Kosa', 'age': 28}
]
```

Using a lambda function.

```python
result = list(
    filter(lambda person: person["age"] > 25, people)
)

print(result)
```

Output

```
[
 {'name': 'Prav', 'age': 27},
 {'name': 'Kosa', 'age': 28}
]
```

[⬆ Back to Top](#-table-of-contents)

---

# 🌍 Practical Examples

## Filter Positive Numbers

```python
numbers = [-5, -2, 0, 3, 8, 10]

positive = list(
    filter(lambda x: x > 0, numbers)
)

print(positive)
```

Output

```
[3, 8, 10]
```

---

## Filter Strings Longer Than Five Characters

```python
words = ["apple", "banana", "kiwi", "watermelon"]

long_words = list(
    filter(lambda word: len(word) > 5, words)
)

print(long_words)
```

Output

```
['banana', 'watermelon']
```

---

## Filter Odd Numbers

```python
numbers = list(range(1,11))

odd = list(
    filter(lambda x: x % 2 != 0, numbers)
)

print(odd)
```

Output

```
[1, 3, 5, 7, 9]
```

[⬆ Back to Top](#-table-of-contents)

---

# ❌ Common Errors

### Forgetting to Convert to a List

Incorrect

```python
result = filter(even, numbers)

print(result)
```

Output

```
<filter object at 0x...>
```

Correct

```python
print(list(result))
```

---

### Returning Non-Boolean Values

Incorrect

```python
def even(x):
    return x
```

The function should return `True` or `False`.

Correct

```python
def even(x):
    return x % 2 == 0
```

---

### Misspelling `lambda`

Incorrect

```python
lamba x: x > 5
```

Correct

```python
lambda x: x > 5
```

[⬆ Back to Top](#-table-of-contents)

---

# ✅ Best Practices

- Use `filter()` when selecting items based on a condition.
- Use lambda functions for simple filtering.
- Use regular functions for complex conditions.
- Convert the filter object into a list if required.
- Keep filtering conditions simple and readable.

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Summary

In this chapter, you learned:

- ✅ What `filter()` is
- ✅ Syntax of `filter()`
- ✅ Using regular functions
- ✅ Using lambda functions
- ✅ Filtering with multiple conditions
- ✅ Filtering dictionaries
- ✅ Practical examples
- ✅ Common errors
- ✅ Best practices

The `filter()` function provides an elegant way to extract elements from an iterable based on one or more conditions.

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Practice Exercises

### Exercise 1

Filter all even numbers from a list.

---

### Exercise 2

Filter all numbers greater than 50.

---

### Exercise 3

Filter names whose length is greater than 4.

---

### Exercise 4

Filter employees whose salary is greater than 50,000.

---

### Exercise 5

Filter students who scored more than 80 marks.

---

## 🎯 What's Next?

In **Day 10**, you'll learn about **`reduce()` in Python**, including:

- 🔹 Introduction to `reduce()`
- 🔹 Syntax
- 🔹 Using `reduce()` with Lambda Functions
- 🔹 Mathematical Operations
- 🔹 Practical Examples
- 🔹 Best Practices

Happy Coding! 🚀