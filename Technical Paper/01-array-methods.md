# Array (List) Methods

Python does not have a dedicated array type in its core syntax the way languages like Java do. Instead, the built-in `list` object is used to store ordered, mutable collections of items. Lists support a wide range of methods for adding, removing, and rearranging elements.

## Commonly Used List Methods

* `append(x)` - adds a single item `x` to the end of the list.
* `extend(iterable)` - adds all items from another iterable to the end of the list.
* `insert(i, x)` - inserts item `x` at index `i`.
* `remove(x)` - removes the first item whose value equals `x`.
* `pop(i)` - removes and returns the item at index `i` (defaults to the last item).
* `sort()` - sorts the list in place, ascending by default.
* `reverse()` - reverses the order of elements in place.
* `index(x)` - returns the index of the first item matching `x`.
* `count(x)` - returns the number of times `x` appears in the list.

## Example

```python
numbers = [4, 2, 9, 1]
numbers.append(7)
numbers.sort()
print(numbers)  # [1, 2, 4, 7, 9]
```

For numeric computation involving true fixed-type arrays, the `array` module or the `numpy` library is typically used instead of plain lists.
