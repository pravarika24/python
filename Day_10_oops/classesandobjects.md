# 📘 Day 10: Classes and Objects in Python

> Object-Oriented Programming (OOP) is a programming paradigm that uses **objects** to model real-world entities. Objects are created from **classes**, which act as blueprints defining the data (attributes) and behavior (methods) of those objects.

---

## 📑 Table of Contents

- [Introduction to OOP](#-introduction-to-oop)
- [What is a Class?](#-what-is-a-class)
- [What is an Object?](#-what-is-an-object)
- [Creating Your First Class](#-creating-your-first-class)
- [Instance Variables](#-instance-variables)
- [Constructors (`__init__()`)](#-constructors-__init__)
- [Instance Methods](#-instance-methods)
- [Practical Example: Bank Account](#-practical-example-bank-account)
- [Common Errors](#-common-errors)
- [Best Practices](#-best-practices)
- [Summary](#-summary)
- [Practice Exercises](#-practice-exercises)

---

# 📖 Introduction to OOP

Object-Oriented Programming (OOP) is a programming paradigm that organizes programs around **objects** rather than functions.

Objects represent real-world entities such as:

- Cars
- Students
- Employees
- Bank Accounts
- Books

Each object contains:

- **Attributes** (Data)
- **Methods** (Functions)

Example:

```
Car
│
├── Windows
├── Doors
├── Engine Type
└── Drive()
```

[⬆ Back to Top](#-table-of-contents)

---

# 🏛️ What is a Class?

A **class** is a blueprint used to create objects.

It defines:

- Attributes (Variables)
- Methods (Functions)

Syntax

```python
class ClassName:
    pass
```

Example

```python
class Car:
    pass
```

Here, `Car` is a class.

[⬆ Back to Top](#-table-of-contents)

---

# 🚗 What is an Object?

An **object** is an instance of a class.

Objects are created using the class name.

```python
class Car:
    pass

audi = Car()

bmw = Car()
```

Check the object type.

```python
print(type(audi))
```

Output

```
<class '__main__.Car'>
```

Print the object.

```python
print(audi)
```

Output

```
<__main__.Car object at 0x...>
```

[⬆ Back to Top](#-table-of-contents)

---

# 🧱 Creating Your First Class

You can dynamically add attributes to an object.

```python
class Car:
    pass

audi = Car()

audi.windows = 4

print(audi.windows)
```

Output

```
4
```

Although valid, this is **not recommended**.

Another object.

```python
tata = Car()

tata.doors = 4
```

Trying to access a non-existing attribute

```python
print(tata.windows)
```

Raises

```
AttributeError
```

> **Best Practice:** Always initialize attributes using a constructor.

[⬆ Back to Top](#-table-of-contents)

---

# 🏷️ Instance Variables

Instance variables belong to individual objects.

They are initialized inside the constructor.

```python
class Dog:

    def __init__(self, name, age):

        self.name = name

        self.age = age
```

Create objects.

```python
dog1 = Dog("Buddy", 3)

print(dog1.name)

print(dog1.age)
```

Output

```
Buddy

3
```

Another object.

```python
dog2 = Dog("Lucy", 4)

print(dog2.name)

print(dog2.age)
```

Output

```
Lucy

4
```

Each object has its own copy of the instance variables.

[⬆ Back to Top](#-table-of-contents)

---

# 🔨 Constructors (`__init__()`)

The constructor (`__init__()`) is automatically called whenever an object is created.

```python
class Dog:

    def __init__(self, name, age):

        self.name = name

        self.age = age
```

Benefits of constructors:

- Initialize object attributes
- Reduce repetitive code
- Ensure objects are created with valid data

[⬆ Back to Top](#-table-of-contents)

---

# ⚙️ Instance Methods

Methods define the behavior of an object.

```python
class Dog:

    def __init__(self, name, age):

        self.name = name

        self.age = age

    def bark(self):

        print(f"{self.name} says Woof!")
```

Create objects.

```python
dog1 = Dog("Buddy", 3)

dog2 = Dog("Lucy", 4)
```

Call methods.

```python
dog1.bark()

dog2.bark()
```

Output

```
Buddy says Woof!

Lucy says Woof!
```

[⬆ Back to Top](#-table-of-contents)

---

# 🏦 Practical Example: Bank Account

Let's model a simple bank account using a class.

```python
class BankAccount:

    def __init__(self, owner, balance=0):

        self.owner = owner

        self.balance = balance

    def deposit(self, amount):

        self.balance += amount

        print(
            f"${amount} deposited. "
            f"New balance: ${self.balance}"
        )

    def withdraw(self, amount):

        if amount > self.balance:

            print("Insufficient funds.")

        else:

            self.balance -= amount

            print(
                f"${amount} withdrawn. "
                f"New balance: ${self.balance}"
            )

    def get_balance(self):

        return self.balance
```

Create an account.

```python
account = BankAccount("Krish", 5000)
```

Check balance.

```python
print(account.get_balance())
```

Output

```
5000
```

Deposit money.

```python
account.deposit(1000)
```

Output

```
$1000 deposited. New balance: $6000
```

Withdraw money.

```python
account.withdraw(300)
```

Output

```
$300 withdrawn. New balance: $5700
```

Check updated balance.

```python
print(account.get_balance())
```

Output

```
5700
```

[⬆ Back to Top](#-table-of-contents)

---

# 🌍 Real-World Applications

Classes and objects are used in almost every software application.

Examples:

- 🚗 Vehicle Management Systems
- 🏦 Banking Applications
- 🏫 Student Management Systems
- 🛒 E-commerce Websites
- 📱 Mobile Applications
- 🎮 Game Development

[⬆ Back to Top](#-table-of-contents)

---

# ❌ Common Errors

## Missing `self`

Incorrect

```python
def bark():
```

Correct

```python
def bark(self):
```

---

## Incorrect Constructor

Incorrect

```python
def __init(self):
```

Correct

```python
def __init__(self):
```

---

## Incorrect Class Name

Incorrect

```python
dog1 = dog("Buddy", 3)
```

Correct

```python
dog1 = Dog("Buddy", 3)
```

---

## Missing Colon

Incorrect

```python
class Dog
```

Correct

```python
class Dog:
```

---

## Accessing Undefined Attributes

```python
print(tata.windows)
```

Raises

```
AttributeError
```

Always initialize attributes inside the constructor.

[⬆ Back to Top](#-table-of-contents)

---

# ✅ Best Practices

- Initialize attributes inside `__init__()`.
- Use meaningful class names (PascalCase).
- Use meaningful variable names.
- Keep methods focused on a single responsibility.
- Avoid dynamically creating attributes whenever possible.
- Use instance methods to operate on object data.

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Summary

In this chapter, you learned:

- ✅ Object-Oriented Programming (OOP)
- ✅ Classes
- ✅ Objects
- ✅ Instance Variables
- ✅ Constructors (`__init__()`)
- ✅ Instance Methods
- ✅ Practical Bank Account Example
- ✅ Common Errors
- ✅ Best Practices

Classes and objects form the foundation of Object-Oriented Programming. They allow developers to model real-world entities, organize code efficiently, and build scalable, reusable applications.

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Practice Exercises

### Exercise 1

Create a `Student` class with:

- Name
- Age
- Grade

Display the student's details.

---

### Exercise 2

Create a `Rectangle` class with:

- Length
- Width

Add methods to calculate:

- Area
- Perimeter

---

### Exercise 3

Create an `Employee` class with:

- Employee ID
- Name
- Salary

Add a method to increase the salary.

---

### Exercise 4

Create a `Car` class with:

- Brand
- Model
- Year

Add a `start()` method.

---

### Exercise 5

Extend the `BankAccount` class by adding:

- Transfer money
- Display account information

---

## 🎯 What's Next?

In upcoming lessons, you'll learn about **Static Methods, Class Methods, and Class Variables**, including:

- 🏷️ Class Variables
- 🧩 Instance Variables
- ⚙️ Static Methods
- 🏛️ Class Methods
- 🌍 Practical Examples

Happy Coding! 🚀