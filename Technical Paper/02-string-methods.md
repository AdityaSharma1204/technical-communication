# String Methods

Strings in Python are immutable sequences of characters, and the `str` class provides many built-in methods for text manipulation without needing external libraries.

## Frequently Used String Methods

* `upper()` / `lower()` - converts the string to uppercase or lowercase.
* `strip()` - removes leading and trailing whitespace.
* `split(sep)` - splits a string into a list based on a separator.
* `join(iterable)` - joins elements of an iterable into a single string using the string as a separator.
* `replace(old, new)` - replaces occurrences of a substring with another.
* `find(sub)` - returns the lowest index where the substring is found, or -1 if not found.
* `startswith(prefix)` / `endswith(suffix)` - checks whether the string starts or ends with the given text.
* `format()` / f-strings - used for string interpolation.

## Example

```python
name = "  Aditya  "
clean_name = name.strip().lower()
print(f"Hello, {clean_name}")  # Hello, aditya
```
