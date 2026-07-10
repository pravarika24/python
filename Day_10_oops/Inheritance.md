# 📘 Day 10: Inheritance in Python

> Inheritance is one of the four fundamental principles of Object-Oriented Programming (OOP). It allows one class to inherit the properties and methods of another class, promoting **code reusability**, **extensibility**, and **hierarchical relationships** between classes.

---

## 📑 Table of Contents

- [Introduction to Inheritance](#-introduction-to-inheritance)
- [Why Use Inheritance?](#-why-use-inheritance)
- [Single Inheritance](#-single-inheritance)
- [The `super()` Function](#-the-super-function)
- [Multiple Inheritance](#-multiple-inheritance)
- [Method Resolution Order (MRO)](#-method-resolution-order-mro)
- [Common Errors](#-common-errors)
- [Best Practices](#-best-practices)
- [Summary](#-summary)
- [Practice Exercises](#-practice-exercises)

---

# 📖 Introduction to Inheritance

**Inheritance** is a mechanism in Object-Oriented Programming (OOP) that allows one class (child class) to inherit the properties and methods of another class (parent class).

This promotes:

- Code Reusability
- Extensibility
- Reduced Code Duplication
- Better Code Organization

### Terminology

- **Parent Class (Base Class)** → The class whose properties are inherited.
- **Child Class (Derived Class)** → The class that inherits from the parent class.

[⬆ Back to Top](#-table-of-contents)

---

# ⭐ Why Use Inheritance?

Without inheritance, common code has to be written repeatedly.

With inheritance:

- Write common functionality once.
- Extend functionality in child classes.
- Override methods when needed.

Example:

```
Vehicle
   │
   ├── Car
   │      ├── Tesla
   │      └── BMW
   │
   └── Bike
```

[⬆ Back to Top](#-table-of-contents)

---

# 🚗 Single Inheritance

Single inheritance means one child class inherits from one parent class.

## Parent Class

```python
class Car:

    def __init__(self, windows, doors, engine_type):

        self.windows = windows
        self.doors = doors
        self.engine_type = engine_type

    def drive(self):

        print(f"The person drives a {self.engine_type} car.")
```

Create an object.

```python
car1 = Car(4, 5, "Petrol")

car1.drive()
```

Output

```
The person drives a Petrol car.
```

---

## Child Class

```python
class Tesla(Car):

    def __init__(
        self,
        windows,
        doors,
        engine_type,
        is_self_driving
    ):

        super().__init__(
            windows,
            doors,
            engine_type
        )

        self.is_self_driving = is_self_driving

    def self_driving(self):

        print(
            f"Tesla supports self-driving: {self.is_self_driving}"
        )
```

Create an object.

```python
tesla1 = Tesla(
    4,
    5,
    "Electric",
    True
)

tesla1.self_driving()

tesla1.drive()
```

Output

```
Tesla supports self-driving: True

The person drives a Electric car.
```

> **Note:** `Tesla` inherits the `drive()` method from the `Car` class.

[⬆ Back to Top](#-table-of-contents)

---

# 🔄 The `super()` Function

The `super()` function is used to call methods or constructors of the parent class.

Example

```python
super().__init__(
    windows,
    doors,
    engine_type
)
```

Benefits of `super()`:

- Avoids code duplication
- Initializes parent class attributes
- Makes code cleaner and easier to maintain

[⬆ Back to Top](#-table-of-contents)

---

# 🐶 Multiple Inheritance

Multiple inheritance allows a class to inherit from more than one parent class.

## Base Class 1

```python
class Animal:

    def __init__(self, name):

        self.name = name

    def speak(self):

        print("Subclasses should implement this method.")
```

---

## Base Class 2

```python
class Pet:

    def __init__(self, owner):

        self.owner = owner
```

---

## Derived Class

```python
class Dog(Animal, Pet):

    def __init__(self, name, owner):

        Animal.__init__(self, name)

        Pet.__init__(self, owner)

    def speak(self):

        return f"{self.name} says Woof!"
```

Create an object.

```python
dog = Dog("Buddy", "Prav")

print(dog.speak())

print(f"Owner: {dog.owner}")
```

Output

```
Buddy says Woof!

Owner: Prav
```

> **Note:** `Dog` inherits properties from both `Animal` and `Pet`.

[⬆ Back to Top](#-table-of-contents)

---

# 🧭 Method Resolution Order (MRO)

When a class inherits from multiple parent classes, Python follows the **Method Resolution Order (MRO)** to determine which method should be executed.

Example

```python
print(Dog.__mro__)
```

Output (simplified)

```
Dog

Animal

Pet

object
```

You can also use:

```python
help(Dog)
```

to see the inheritance hierarchy.

[⬆ Back to Top](#-table-of-contents)

---

# 🌍 Real-World Example

Suppose a company has different types of employees.

```python
class Employee:

    def work(self):

        print("Employee is working.")
```

```python
class Manager(Employee):

    def manage(self):

        print("Managing the team.")
```

```python
class Developer(Employee):

    def code(self):

        print("Writing Python code.")
```

Create objects.

```python
manager = Manager()

developer = Developer()

manager.work()
manager.manage()

developer.work()
developer.code()
```

Output

```
Employee is working.

Managing the team.

Employee is working.

Writing Python code.
```

Inheritance avoids rewriting the `work()` method.

[⬆ Back to Top](#-table-of-contents)

---

# ❌ Common Errors

## Missing Colon

Incorrect

```python
class Car()
```

Correct

```python
class Car:
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

## Forgetting `super()`

If the parent constructor initializes important attributes, forgetting `super()` can lead to errors.

---

## Misspelled Class Names

Incorrect

```python
telsa = Telsa()
```

Correct

```python
tesla = Tesla()
```

---

## Using `print()` Inside `return`

Incorrect

```python
return print("Hello")
```

Return the value instead.

[⬆ Back to Top](#-table-of-contents)

---

# ✅ Best Practices

- Use inheritance only when there is an **"is-a"** relationship.
- Keep inheritance hierarchies simple.
- Prefer `super()` over directly calling parent constructors.
- Avoid deep inheritance chains.
- Override methods only when necessary.
- Use meaningful class names.

[⬆ Back to Top](#-table-of-contents)

---

# 📚 Summary

In this chapter, you learned:

- ✅ Introduction to inheritance
- ✅ Parent and child classes
- ✅ Single inheritance
- ✅ The `super()` function
- ✅ Multiple inheritance
- ✅ Method Resolution Order (MRO)
- ✅ Real-world examples
- ✅ Common mistakes
- ✅ Best practices

Inheritance is one of the most powerful OOP concepts because it enables code reuse and allows developers to build scalable and maintainable applications.

[⬆ Back to Top](#-table-of-contents)

---

# 💻 Practice Exercises

### Exercise 1

Create a `Vehicle` class and derive:

- Car
- Bike

Add a common `start()` method.

---

### Exercise 2

Create an `Employee` class and derive:

- Manager
- Developer
- Tester

Override the `work()` method.

---

### Exercise 3

Create a multiple inheritance example using:

- Person
- Employee
- Manager

---

### Exercise 4

Use `super()` to initialize parent class attributes.

---

### Exercise 5

Print the Method Resolution Order (MRO) of a class using:

```python
ClassName.__mro__
```

---

## 🎯 What's Next?

In upcoming lessons, you'll learn about **Encapsulation and Abstraction in Python**, including:

- 🔒 Public, Protected, and Private Members
- 🎭 Encapsulation
- 🧩 Abstraction
- 🏛️ Abstract Classes
- 🌍 Real-world Examples

Happy Coding! 🚀