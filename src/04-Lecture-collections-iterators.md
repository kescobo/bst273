# Collections and Iterators

## Outline

- Collections of data
- Lists (ordered collections)
- Dictionaries (referenced collection)
- Sets (unordered collection of unique values)
- Iterators and loops

## Learning Objectives

After completing this lesson, you should be able to:

1. Explain the differences between lists, dictionaries and sets.
2. Identify the best collection type for a particular application.
3. Iterate over a collection and modify the contents.
4. Write a function that modifies a list.

## Review of scalars

Integers and floats represent numbers.

```python
integer  = 2 + 2
```
```python
flt = 26.7 * 0.15
```

### Strings are sequences of characters

```python
st = 'How' + ' ' + 'now' + ' ' + 'brown' + ' ' + 'cow' + '?'
```

## Collections are groups of related objects

- The contents of collections can be scalars of different types, or even other collections
- The best type of collection depends on the application
    - Does the content have an order?
    - How do you plan to access the content?
- "Data Structures" represent an entire CS course... there are many other collection types than what we'll discuss here

### Common features of collections

- they may contain 0 or more entries (they can be empty)
    - entries can be scalars or other collections
- they are iterable (`for` loops touch each entry exactly once)
- they are mutable (you can add, remove, or modify entries)
- they are indexable (you can access individual entries with a unique "index")

## Lists (vectors) are ordered collections

```python
my_list = [1, 'z', 2.4, 42, 1]
my_list
```

Iterating through a list returns the elements of the list in order

```python
for element in my_list:
    print(element)
```

### List "indexing"

We can also access items at particular locations in the list.

WARNING: in python, counting starts at `0`, not `1`.
In other words, to get the **third** element in `my_list`:

```python
my_list
```
```python
my_list[2]
```

Like a variable, we can perform operations on the items in a list.

```python
my_list[2] * 4
```

### Figuring out how many elements are in a list

The `len()` function ("length") tells us how many items are in a list.

```python
len(my_list)
```

You may be tempted to use len to get the last item in the list...

```python
list_length = len(my_list)
my_list[list_length]
```

This error is telling us that the `index` (in this case `5`) is "out of range."
In other words, the index `5` is "off the end" of the list.
This is because python counts from 0...
a list with `len(list) == 5` has indices `[0,1,2,3,4]`.

### Getting the last element in a list

```python
my_list[-1]
```


### Modiying lists

Lists are "mutable", meaning we can change them.

```python
my_list[1] = 10
my_list
```

```python
my_list.append('a new entry')
my_list
```

```python
my_list.insert(4, 'another new entry')
my_list
```

## A quick aside

Don't forget to google!

"How do I add something to a list in python?"

**Question 1**

Remove all of the strings from the list `my_list2`:

```python
my_list2 = ['a', 20, 2.3, 4.9, 'b', 7]
```

```py
# use this cell to figure out the code, then copy and paste it
# into the answer box in the quiz
```

## Dictionaries are unordered collections with arbitrary "keys"

```python
my_dict = {"Ada": 0, "Bodhidharma": 1, "César": 2}
my_dict
```

Entries in a dict are accessed by their keys

```python
my_dict["Ada"]
```

### Iterating through a dictionary provides keys

NOTE: The order of the keys is unrelated to the way the dictionary was constructed

```python
for k in my_dict:
    print(k)
```
