# Objects and Object Oriented Programming

Python is a multi-paradigm language that supports object oriented programming through classes and objects. A class acts as a blueprint, and an object is an instance created from that blueprint. Python OOP is built around four core principles: encapsulation, inheritance, polymorphism, and abstraction.

## Key Building Blocks

* `class` - defines a new object type.
* `__init__` - the constructor method, called automatically when an object is created.
* `self` - refers to the current instance of the class.
* Inheritance - allows a class to reuse and extend behavior from a parent class using `class Child(Parent):`.
* Polymorphism - allows different classes to implement the same method name differently.

## Example

```python
class Vehicle:
    def __init__(self, brand):
        self.brand = brand

    def description(self):
        return f"This vehicle is made by {self.brand}"

class Car(Vehicle):
    def description(self):
        return f"This car is made by {self.brand}"

v = Car("Toyota")
print(v.description())  # This car is made by Toyota
```

Compared to Java, Python classes are more lightweight since access modifiers are conventional (prefixing with `_` or `__`) rather than strictly enforced by the language.
