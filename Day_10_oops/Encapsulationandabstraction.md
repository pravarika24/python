# 📘 Day 10: Encapsulation and Abstraction in Python

> Encapsulation and Abstraction are two fundamental principles of Object-Oriented Programming (OOP). They help in designing secure, maintainable, reusable, and scalable applications by controlling data access and hiding implementation details.

---

## 📑 Table of Contents

- [Introduction to Encapsulation and Abstraction](#-introduction-to-encapsulation-and-abstraction)
- [What is Encapsulation?](#-what-is-encapsulation)
- [Access Modifiers in Python](#-access-modifiers-in-python)
- [Public Members](#-public-members)
- [Protected Members](#-protected-members)
- [Private Members](#-private-members)
- [Getter and Setter Methods](#-getter-and-setter-methods)
- [What is Abstraction?](#-what-is-abstraction)
- [Abstract Base Classes](#-abstract-base-classes)
- [Practical Example](#-practical-example)
- [Common Errors](#-common-errors)
- [Best Practices](#-best-practices)
- [Summary](#-summary)
- [Practice Exercises](#-practice-exercises)

---

# 📖 Introduction to Encapsulation and Abstraction

Encapsulation and Abstraction are two important concepts in Object-Oriented Programming.

### Encapsulation

Encapsulation means **wrapping data (variables) and methods (functions)** into a single unit (class) and restricting direct access to the data.

### Abstraction

Abstraction means **hiding the implementation details** and exposing only the necessary functionality to the user.

Together, these principles make applications:

- More secure
- Easier to maintain
- Easier to reuse
- Less complex

[⬆ Back to Top](#-table-of-contents)

---

# 🔒 What is Encapsulation?

Encapsulation is the process of combining data and methods into one class while controlling access to the data.

Benefits:

- Prevents accidental modification
- Protects sensitive information
- Improves code organization
- Makes programs easier to maintain

[⬆ Back to Top](#-table-of-contents)

---

# 🛡️ Access Modifiers in Python

Python supports three types of access modifiers.

| Access Modifier | Syntax | Accessibility |
|-----------------|--------|---------------|
| Public | `name` | Accessible from anywhere |
| Protected | `_name` | Accessible within the class and subclasses |
| Private | `__name` | Accessible only within the class |

> **Note:** Python doesn't enforce strict access control like Java or C++; these are naming conventions with varying levels of protection.

[⬆ Back to Top](#-table-of-contents)

---

# 🌍 Public Members

Public members can be accessed from anywhere.

```python
class Person:

    def __init__(self, name, age):

        self.name = name
        self.age = age
```

Create an object.

```python
person = Person("Prav", 32)

print(person.name)

print(person.age)
```

Output

```
Prav

32
```

View available attributes.

```python
print(dir(person))
```

Both `name` and `age` appear because they are public.

[⬆ Back to Top](#-table-of-contents)

---

# 🔐 Private Members

Private members begin with **double underscores (`__`)**.

```python
class Person:

    def __init__(self, name, age, gender):

        self.__name = name
        self.__age = age
        self.gender = gender

    def get_name(self):

        return self.__name
```

Create an object.

```python
person = Person("prav", 34, "Male")

print(person.get_name())
```

Output

```
prav
```

Trying to access a private variable directly

```python
print(person.__name)
```

Produces

```
AttributeError
```

> **Note:** Private members cannot be accessed directly outside the class.

[⬆ Back to Top](#-table-of-contents)

---

# 🟡 Protected Members

Protected members begin with a **single underscore (`_`)**.

```python
class Person:

    def __init__(self, name, age, gender):

        self._name = name
        self._age = age
        self.gender = gender
```

Child class

```python
class Employee(Person):

    def __init__(self, name, age, gender):

        super().__init__(name, age, gender)

    def display(self):

        print(self._name)
```

Create an object.

```python
employee = Employee("Prav", 27, "Female")

employee.display()
```

Output

```
Prav
```

> **Note:** Protected members should only be accessed within the class and its subclasses.

[⬆ Back to Top](#-table-of-contents)

---

# 🎯 Getter and Setter Methods

Getter methods retrieve private data.

Setter methods modify private data safely.

```python
class Person:

    def __init__(self, name, age):

        self.__name = name
        self.__age = age

    def get_name(self):

        return self.__name

    def get_age(self):

        return self.__age

    def set_name(self, name):

        self.__name = name

    def set_age(self, age):

        if age > 0:
            self.__age = age
        else:
            print("Age cannot be negative.")
```

Using getters and setters

```python
person = Person("prav", 34)

print(person.get_name())

print(person.get_age())

person.set_age(35)

print(person.get_age())

person.set_age(-5)
```

Output

```
prav

34

35

Age cannot be negative.
```

> **Why use setters?** They allow validation before modifying data.

[⬆ Back to Top](#-table-of-contents)

---

# 🎭 What is Abstraction?

Abstraction hides implementation details and exposes only essential features.

The user knows **what** a class does, not **how** it does it.

Benefits:

- Reduces complexity
- Improves maintainability
- Promotes consistency
- Encourages modular design

Python implements abstraction using the **`abc`** module.

[⬆ Back to Top](#-table-of-contents)

---

# 🏛️ Abstract Base Classes

Import the required module.

```python
from abc import ABC, abstractmethod
```

Create an abstract class.

```python
class Vehicle(ABC):

    def drive(self):

        print("The vehicle is used for driving.")

    @abstractmethod
    def start_engine(self):

        pass
```

> **Note:** An abstract method has no implementation in the base class. Every child class **must** implement it.

[⬆ Back to Top](#-table-of-contents)

---

# 🚗 Practical Example

```python
from abc import ABC, abstractmethod

class Vehicle(ABC):

    def drive(self):

        print("The vehicle is used for driving.")

    @abstractmethod
    def start_engine(self):

        pass
```

Derived class

```python
class Car(Vehicle):

    def start_engine(self):

        print("Car engine started.")
```

Function

```python
def operate_vehicle(vehicle):

    vehicle.start_engine()
```

Create an object

```python
car = Car()

car.drive()

operate_vehicle(car)
```

Output

```
The vehicle is used for driving.

Car engine started.
```

> Since `Vehicle` contains an abstract method, you **cannot** create an object of it.

```python
vehicle = Vehicle()
```

Raises

```
TypeError
```

[⬆ Back to Top](#-table-of-contents)

---

# ❌ Common Errors

## Accessing Private Variables Directly

Incorrect

```python
print(person.__name)
```

Use

```python
person.get_name()
```

instead.

---

## Forgetting `@abstractmethod`

If a method should be mandatory for child classes, decorate it with

```python
@abstractmethod
```

---

## Instantiating an Abstract Class

Incorrect

```python
vehicle = Vehicle()
```

Produces

```
TypeError
```

---

## Missing `super().__init__()`

When inheriting, forgetting to initialize the parent class may leave required attributes uninitialized.

[⬆ Back to Top](#-table-of-contents)

---

# ✅ Best Practices

- Keep sensitive data private.
- Use getters and setters when validation is required.
- Prefer abstraction for common interfaces.
- Use abstract classes when child classes must implement specific methods.
- Use meaningful class and method names.
- Expose only necessary functionality.

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Summary

In this chapter, you learned:

- ✅ Encapsulation
- ✅ Public members
- ✅ Protected members
- ✅ Private members
- ✅ Getter methods
- ✅ Setter methods
- ✅ Abstraction
- ✅ Abstract Base Classes (ABC)
- ✅ Real-world examples
- ✅ Common mistakes
- ✅ Best practices

Encapsulation protects an object's internal data, while abstraction hides unnecessary implementation details. Together, they make applications more secure, modular, and maintainable.

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Practice Exercises

### Exercise 1

Create a `Student` class with private variables:

- Name
- Roll Number
- Marks

Implement getters and setters.

---

### Exercise 2

Prevent setting a negative salary using a setter method.

---

### Exercise 3

Create an abstract class `Shape` with an abstract method:

```python
area()
```

Implement it in:

- Circle
- Rectangle
- Triangle

---

### Exercise 4

Create an abstract class `Payment` with:

```python
pay()
```

Implement it in:

- CreditCard
- UPI
- PayPal

---

### Exercise 5

Build a `BankAccount` class using encapsulation.

Only allow deposits and withdrawals through methods.

---

## 🎯 What's Next?

In upcoming lessons, you'll learn about **Decorators in Python**, including:

- 🎀 What are Decorators?
- 🔄 Function Wrappers
- 📝 `@decorator` Syntax
- ⏱️ Practical Logging and Timing Examples
- 🚀 Real-world Use Cases

Happy Coding! 🚀