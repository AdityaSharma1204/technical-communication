# Decorators

A decorator is a function that wraps another function or method to extend or modify its behavior without permanently changing its source code. Decorators are widely used for logging, access control, timing, and caching. They rely on the fact that functions are first-class objects in Python and can be passed around like any other variable.

## Example

```python
import functools

def log_execution(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        print(f"Running {func.__name__}")
        result = func(*args, **kwargs)
        print(f"Finished {func.__name__}")
        return result
    return wrapper

@log_execution
def add(a, b):
    return a + b

add(3, 5)
```

Python also ships with built-in decorators such as `@staticmethod`, `@classmethod`, and `@property`, which are commonly used inside class definitions.
