# Object-Oriented Programming (OOP) in Python

Object-Oriented Programming, commonly known as OOP, is a programming style that organizes code around objects rather than functions and logic alone. An object is a bundle of data (attributes) and behaviour (methods) that represents a real-world entity. Python fully supports OOP and makes it easy to model real-world problems using classes and objects. The four main pillars of OOP are encapsulation, inheritance, polymorphism, and abstraction. Below, I have explained each pillar in my own words along with code samples I wrote to demonstrate the concept.

## 1. Class and Object

A class is a blueprint for creating objects. It defines the attributes and methods that the objects created from it will have. An object is an instance of a class, created using that blueprint.

```python
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

    def display_info(self):
        print(f"Car: {self.brand} {self.model}")

my_car = Car("Toyota", "Fortuner")
my_car.display_info()
```

## 2. Encapsulation

Encapsulation means wrapping data and the methods that operate on that data into a single unit, and restricting direct access to some of the object's components. In Python, we achieve this using single underscore (protected) or double underscore (private) naming conventions, along with the `@property` decorator to control how attributes are read or modified.

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance

    @property
    def balance(self):
        return self.__balance

    @balance.setter
    def balance(self, amount):
        if amount < 0:
            print("Balance cannot be negative.")
        else:
            self.__balance = amount

account = BankAccount(5000)
print(account.balance)
account.balance = 7000
print(account.balance)
```

In this example, the `__balance` attribute is private and can only be accessed or updated through the `balance` property, which also validates the new value before setting it.

## 3. Inheritance

Inheritance allows a class (child class) to acquire the attributes and methods of another class (parent class). This helps in reusing code and building a hierarchy of related classes.

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        print(f"{self.name} makes a sound.")

class Dog(Animal):
    def speak(self):
        print(f"{self.name} barks.")

class Cat(Animal):
    def speak(self):
        print(f"{self.name} meows.")

dog = Dog("Bruno")
cat = Cat("Whiskers")
dog.speak()
cat.speak()
```

Here, both `Dog` and `Cat` inherit from `Animal` and override the `speak` method with their own specific behaviour.

## 4. Polymorphism

Polymorphism means the same method name can behave differently depending on the object calling it. In the inheritance example above, calling `speak()` on a `Dog` object and a `Cat` object produces different outputs, even though both classes use the same method name. Python also supports polymorphism through duck typing, where an object's suitability is determined by the presence of certain methods, not its actual type.

```python
def make_it_speak(animal):
    animal.speak()

make_it_speak(dog)
make_it_speak(cat)
```

The `make_it_speak` function works with any object that has a `speak` method, regardless of its class, which shows how polymorphism promotes flexible and reusable code.

## 5. Abstraction

Abstraction means hiding complex implementation details and exposing only the necessary features to the user. Python provides the `abc` module to create abstract base classes, which define methods that must be implemented by any subclass.

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

rect = Rectangle(5, 3)
print(f"Area: {rect.area()}")
```

Since `Shape` is an abstract class, it cannot be instantiated directly. Any subclass, like `Rectangle`, must implement the `area` method, ensuring a consistent structure across all shape classes.

## Summary

OOP in Python revolves around classes and objects, and its four pillars work together to make code more organized, reusable, and secure. Encapsulation protects data using private attributes and properties. Inheritance allows classes to reuse and extend behaviour from other classes. Polymorphism lets the same method name behave differently across classes. Abstraction hides implementation details and enforces a consistent structure through abstract classes. Understanding these concepts is essential for writing clean and maintainable Python code, especially in larger projects.

## References

* Python official documentation, Classes: https://docs.python.org/3/tutorial/classes.html
* Python official documentation, abc module: https://docs.python.org/3/library/abc.html
* Real Python, Object-Oriented Programming in Python 3: https://realpython.com/python3-object-oriented-programming/
