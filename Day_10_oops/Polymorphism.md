# 📘 Day 10: Polymorphism in Python

> Polymorphism is one of the four fundamental principles of Object-Oriented Programming (OOP). It allows objects of different classes to be treated through a common interface, enabling the same method to perform different actions depending on the object.

---

## 📑 Table of Contents

- [Introduction to Polymorphism](#-introduction-to-polymorphism)
- [Method Overriding](#-method-overriding)
- [Polymorphism with Functions](#-polymorphism-with-functions)
- [Polymorphism with Abstract Base Classes](#-polymorphism-with-abstract-base-classes)
- [Common Errors](#-common-errors)
- [Best Practices](#-best-practices)
- [Summary](#-summary)
- [Practice Exercises](#-practice-exercises)

---

# 📖 Introduction to Polymorphism

**Polymorphism** means **"many forms."**

It allows the same method or function name to behave differently depending on the object that calls it.

In Python, polymorphism is mainly achieved using:

- Method Overriding
- Duck Typing
- Abstract Base Classes (ABCs)

### Benefits

- Improves code reusability
- Makes programs flexible
- Reduces code duplication
- Supports extensibility

[⬆ Back to Top](#-table-of-contents)

---

# 🔄 Method Overriding

Method overriding allows a child class to provide its own implementation of a method already defined in the parent class.

## Base Class

```python
class Animal:

    def speak(self):
        return "Sound of the animal"
```

---

## Derived Class - Dog

```python
class Dog(Animal):

    def speak(self):
        return "Woof!"
```

---

## Derived Class - Cat

```python
class Cat(Animal):

    def speak(self):
        return "Meow!"
```

---

## Demonstrating Polymorphism

```python
def animal_speak(animal):

    print(animal.speak())
```

```python
dog = Dog()
cat = Cat()

print(dog.speak())

print(cat.speak())

animal_speak(dog)

animal_speak(cat)
```

### Output

```
Woof!

Meow!

Woof!

Meow!
```

> **Note:** The same function (`animal_speak`) works with different object types.

[⬆ Back to Top](#-table-of-contents)

---

# 🔷 Polymorphism with Functions

Different classes can implement the same method in different ways.

## Base Class

```python
class Shape:

    def area(self):
        return "Area of the shape"
```

---

## Rectangle Class

```python
class Rectangle(Shape):

    def __init__(self, width, height):

        self.width = width
        self.height = height

    def area(self):

        return self.width * self.height
```

---

## Circle Class

```python
class Circle(Shape):

    def __init__(self, radius):

        self.radius = radius

    def area(self):

        return 3.14 * self.radius * self.radius
```

---

## Function

```python
def print_area(shape):

    print(f"The area is {shape.area()}")
```

---

## Calling the Function

```python
rectangle = Rectangle(4, 5)

circle = Circle(3)

print_area(rectangle)

print_area(circle)
```

### Output

```
The area is 20

The area is 28.259999999999998
```

> The same function works for both objects because each class provides its own `area()` implementation.

[⬆ Back to Top](#-table-of-contents)

---

# 🏎️ Polymorphism with Abstract Base Classes

**Abstract Base Classes (ABCs)** define a common interface for related classes.

They ensure that child classes implement specific methods.

Import the required module.

```python
from abc import ABC, abstractmethod
```

---

## Abstract Class

```python
class Vehicle(ABC):

    @abstractmethod
    def start_engine(self):
        pass
```

---

## Car Class

```python
class Car(Vehicle):

    def start_engine(self):
        return "Car engine started."
```

---

## Motorcycle Class

```python
class Motorcycle(Vehicle):

    def start_engine(self):
        return "Motorcycle engine started."
```

---

## Function

```python
def start_vehicle(vehicle):

    print(vehicle.start_engine())
```

---

## Calling the Function

```python
car = Car()

motorcycle = Motorcycle()

start_vehicle(car)

start_vehicle(motorcycle)
```

### Output

```
Car engine started.

Motorcycle engine started.
```

> **Important:** You cannot create an object of an abstract class.

```python
vehicle = Vehicle()
```

Raises

```
TypeError
```

because `Vehicle` contains an abstract method.

[⬆ Back to Top](#-table-of-contents)

---

# 🌍 Real-World Example

Suppose an online payment system supports multiple payment methods.

```python
class Payment:

    def pay(self):
        pass
```

```python
class CreditCard(Payment):

    def pay(self):
        return "Payment using Credit Card"
```

```python
class UPI(Payment):

    def pay(self):
        return "Payment using UPI"
```

```python
class PayPal(Payment):

    def pay(self):
        return "Payment using PayPal"
```

```python
def process_payment(payment):

    print(payment.pay())
```

Calling

```python
process_payment(CreditCard())

process_payment(UPI())

process_payment(PayPal())
```

Output

```
Payment using Credit Card

Payment using UPI

Payment using PayPal
```

This is a practical example of **polymorphism**.

[⬆ Back to Top](#-table-of-contents)

---

# ❌ Common Errors

## Misspelling `@abstractmethod`

Incorrect

```python
@abstraactmethod
```

Correct

```python
@abstractmethod
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

## Incorrect Object Creation

Incorrect

```python
circle = circle(3)
```

Correct

```python
circle = Circle(3)
```

---

## Instantiating an Abstract Class

```python
vehicle = Vehicle()
```

Raises

```
TypeError
```

Abstract classes cannot be instantiated.

[⬆ Back to Top](#-table-of-contents)

---

# ✅ Best Practices

- Use method overriding to customize behavior.
- Use abstract classes when multiple classes share common functionality.
- Prefer polymorphism over long `if-else` statements.
- Keep method names consistent across related classes.
- Design functions to work with base class references.

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Summary

In this chapter, you learned:

- ✅ What polymorphism is
- ✅ Method overriding
- ✅ Polymorphism with functions
- ✅ Abstract Base Classes (ABCs)
- ✅ Real-world examples
- ✅ Common mistakes
- ✅ Best practices

Polymorphism makes Python programs more flexible, reusable, and easier to extend by allowing the same interface to work with different object types.

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Practice Exercises

### Exercise 1

Create a base class `Employee` and derived classes:

- Developer
- Tester
- Manager

Override a method called `work()`.

---

### Exercise 2

Create a `Shape` class with derived classes:

- Triangle
- Square
- Circle

Implement the `area()` method for each.

---

### Exercise 3

Create an abstract class `BankAccount` with the method:

```python
withdraw()
```

Implement it in:

- SavingsAccount
- CurrentAccount

---

### Exercise 4

Build a payment system supporting:

- Credit Card
- Debit Card
- UPI
- PayPal

Use a single function to process all payments.

---

### Exercise 5

Create a polymorphic program for different animals where each animal overrides the `sound()` method.

---

## 🎯 What's Next?

In upcoming lessons, you'll learn about **Duck Typing and Operator Overloading in Python**, including:

- 🦆 Duck Typing
- ➕ Operator Overloading
- 🧩 Magic Methods (`__str__`, `__add__`, etc.)
- 🌍 Real-world Examples

Happy Coding! 🚀