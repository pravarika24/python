# Python Syntax and Semantics

## 1. Single Line Comments

```python
# This is a single line comment
print("Hello World")
```

> Comments are ignored by the Python interpreter.

## 2. Multi Line Comments

```python
'''
This is a
multi line
comment
'''
```

> Python does not have dedicated multi-line comments. We use triple quotes.

## 3. Syntax

Syntax refers to the set of rules that defines the combinations of symbols that are considered to be correctly structured programs in a language.

**Correct Syntax ✓**

```python
x = 10
if x > 5:
    print(x)
```

**Incorrect Syntax ✗**

```python
if x > 5
    print(x)   # missing colon
```

## 4. Semantics

Semantics refers to the meaning or the interpretation of symbols, characters and commands in a language. It is about what the code is supposed to do when it runs.

```python
age = 24
if age > 20:
    print("Adult")   # Semantically meaningful
```

## 5. Basic Syntax Rules in Python

- Statements are written on separate lines.
- Use colon (`:`) after `if`, `for`, `while`, `def`, `class`.
- Indentation is used to define blocks.
- Python is case sensitive.
- Use meaningful variable names.

## 6. Case Sensitivity

```python
name = "prav"
Name = "kosanam"   # Different variables
```

> Python is case sensitive.

## 7. Indentation

Indentation is used to define the structure and hierarchy of the code. All statements within a block must be indented at the same level.

```python
age = 24
if age > 20:
    print(age)   # First print -> inside block
print(age)       # Second print -> outside block
```

## 8. Hello World

```python
print("Hello World")
```

Output:

```
Hello World
```

## 9. Line Continuation

To continue a statement in the next line we use backslash (`\`).

```python
total = 12 + 23 + 32 + 40 + 5 \
        + 40 + 50 + 60
print(total)
```

Output:

```
202
```

## 10. Multiple Statements in Single Line

We can write multiple statements in a single line using semicolon (`;`).

```python
x = 7; y = 12; z = x + y
print(z)
```

Output:

```
19
```

## 11. Understanding Semantics

Python automatically understands the data type of a variable.

```python
age = 23
print(type(age))
name = "prav"
print(type(name))
```

Output:

```
<class 'int'>
<class 'str'>
```

## 12. Type Inference

Python is dynamically typed. During runtime we can change the type of a variable.

```python
var = 32
print(type(var))
var = "hi"
print(type(var))
```

Output:

```
<class 'int'>
<class 'str'>
```

## 13. Common Syntax Errors and How to Avoid Them

**Missing Colon**

```python
# ✗ Incorrect
if age > 20
    print(age)

# ✓ Correct
if age > 20:
    print(age)
```

**Incorrect Indentation**

```python
# ✗ Incorrect
if age > 20:
print(age)

# ✓ Correct
if age > 20:
    print(age)
```

**Missing Parenthesis**

```python
# ✗ Incorrect
print("Hello"

# ✓ Correct
print("Hello")
```

**Invalid Variable Name**

```python
# ✗ Incorrect
1name = "John"

# ✓ Correct
name1 = "John"
```

**Incorrect Capitalization**

```python
# ✗ Incorrect
Print("Hello")

# ✓ Correct
print("Hello")
```

## Best Practices

- Follow PEP 8 coding standards.
- Use 4 spaces for indentation.
- Write one statement per line.
- Use meaningful variable names.
- Add comments to explain your code.
