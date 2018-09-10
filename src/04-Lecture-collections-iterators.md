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

### A quick aside

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

### "Slices" are ranges of indices

Select multiple values using `:`

```python
l3 = [10, 20, 30, 40, 50]
l3[2:4]
```

Select from one value to the end:

```python
l3[3:]
```

## Dictionaries are unordered collections with arbitrary indices

The indices are called "keys",
and the objects referenced by keys are the "values".

```python
my_dict = {"Ada": 0, "Bodhidharma": 1, "César": 2}
my_dict
```

Entries (values) in a dict are accessed by their keys

```python
my_dict["Ada"]
```

### Iterating through a dictionary provides keys

```python
for k in my_dict:
    print(k)
```

Or you can iterate through values using keys:

```python
for k in my_dict:
    print(my_dict[k])
```

### You can get lists of keys and values using the `.keys()` and `.values()` methods

```python
my_dict.keys()
```

```python
my_dict.values()
```

### A quick note on formatting

- One can often take advantage of python's syntax to make code more readable
- For example, spaces after commas, opening brackets etc are ignored

```python
my_dict_formatted = {
    "Ada": 0,
    "Bodhidharma": 1,
    "César": 2
    }

my_dict == my_dict_formatted
```

or

```python
my_dict_formatted = {
    "Ada"         : 0,
    "Bodhidharma" : 1,
    "César"       : 2
    }

my_dict == my_dict_formatted
```

### The order of keys and values does not matter

```python
dict2 = {
    "Bodhidharma" : 1,
    "César"       : 2,
    "Ada"         : 0,
    }
dict2 == my_dict
```

### Dictionary entries can be added, modified, or deleted

```python
my_dict["Kevin"] = 3
my_dict
```

```python
my_dict["Bodhidharma"] = 0 # Will this change the value of `my_dict["Ada"]`?
my_dict
```

```python
my_dict.pop("Kevin")
my_dict
```

## Sets are unordered collections with uniue entries

```python
my_set = {1,2,1,2,1,2}
my_set
```
```python
my_set == {2, 1}
```

### Sets cannot be indexed

```python
my_set[1]
```

But you *can* iterate through them:

```python
for entry in my_set:
    print(entry)
```

### Pay attention to the (lack of) ordering

```python
for entry in {3,2,1,"2"}:
    print(type(entry))
    print(entry)
```

### Sets have some useful functions for comparison

```python
s1 = {'a','b','c','d'}
s2 = {'b','c','d','e'}

s1.intersection(s2) # or s1 & s2
```
```python
s1.difference(s2) # or s1 - s2
```
```python
s1.union(s2) # or s1 | s2
```

NOTE: Set theory is [a whole thing][1] - useful but beyond the scope of this course.

[1]: https://en.wikipedia.org/wiki/Set_theory

### Excercise: other useful set functions

**What values of `my_other_set` will return `True` for the following functions:**

```python
my_first_set = {'Ada', 'Bodhidharma', 'César'}
my_other_set_1 = { } # put at least one string in this set to make the following return True

my_first_set.issuperset(my_other_set_1)
```

```python
my_first_set = {'Ada', 'Bodhidharma', 'César'}
my_other_set_2 = { } # put at least one string in this set to make the following return True

my_first_set.issubset(my_other_set_2)
```

### Set operations can be used to compare other collections

```python
one_more_list = ['a', 'b', 'c', 'd', 'a', 'b']
yet_another_list = ['c', 'd', 'b']

set(one_more_list).union( set(yet_another_list) )
```

### Excercise: using set operations

**What will the return value of the following expression be?**

```python
a_dict = {"Emma"    : "TA",
          "Eric"    : "instructor",
          "Kevin"   : "instructor",
          "Marina"  : "TA",
          "Shirley" : "TA"}

roles = {"instructor", "TA", "student"}

roles.difference( set( a_dict.keys() ) )
```

## Strings are weird

Remember how I said strings can act like scalars or collections of characters?

```python
set("banana")
```
```python
for c in "What's happening?":
    print(c)
```


## Comprehensions

"Comprehensions" are ways to generate collections (lists, dicts, sets) etc
with less typing. The syntax is similar to a `for` loop:

```python
for i in range(5):
    print(i)
```
```python
[i for i in range(5)]
```
```python
[i ** 2 for i in range(5)]
```

### Sets and dictionaries can also be made with comprehensions

```python
{i % 3 for i in range(20)} # what does the % operator do? use google!
```

```python
letters = "abcdefghijklmnopqrstuvwxyz"

{l: n for l, n in zip(letters, range(26))}
```

### How does zip work?

[RTFM = Read the manual][2]
[RTFD = Read the docs][2]

[2]: https://docs.python.org/3/library/functions.html#zip

```python
for i1, i2 in zip([1,2,3,4,5], 'abcde'):
    print(i1)
    print(" ", i2)
```

## X of Ys - nested collections

- So far, all of our collections have held scalars
- But collections can hold other collections too
- For example, you can have a list of lists, or a dict of sets
    - Generally speaking - it's not a good idea to have the `key`s of dicts be collections

```python
teaching_staff = {
    "Eric"  : {
        "position" : "instructor",
        "e-mail"   : "eric.franzosa@hsph.harvard.edu",
        "lectures" : [1,2,5,6,8,11,13,14,15]
        },
    "Kevin" : {
        "position" : "instructor",
        "e-mail"   : "kbonham@broadinstitute.org",
        "lectures" : [3,4,7]
        }
    }

teaching_staff["Eric"]["e-mail"]
```
