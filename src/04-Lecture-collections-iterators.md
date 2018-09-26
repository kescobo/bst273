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
st
```

Actually strings can be thought of as a collection of characters...



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

### Indexing a string

```python
st[4]
```
```python
st[4:13]
```

## Lists (vectors) are ordered collections

```python
my_list = [1, 'z', 2.4, 42, 1]
my_list
```

### Lists can have one or more elements

```python
my_list = [] # this is an "empty" list
```

Add new elements to the end of a list with `.append()`

```python
my_list.append(10)
my_list
```

```python
my_list.append(20)
my_list
```

or with `.extend()`

```python
my_list.extend([30, 40, 50]) # equivalent to `my_list + [30, 40, 50]`
my_list
```

### "Order" for a list means insertion order

```python
my_list.append(3)
my_list
```

If you want the list sorted, use `.sort()`

```python
my_list.sort()
my_list
```

### Iterating through a list returns the elements of the list in order

But first - a quick review of loops

```python
import time

for i in range( 10 ):
    i2 = i ** 2
    print( "i =", i )
    print( "i2=", i2 )
    time.sleep( 2 )
```

### Iterating through a list returns the elements of the list in order

```python
for element in my_list:
    print(element)
```

### List "indexing"

We can also access items at particular locations in the list.

**WARNING**: in python, counting starts at `0`, not `1`.
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

You may be tempted to use `len()` to get the last item in the list...

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

or the second to last:

```python
my_list[-2] # etc
```

### To access a range of values, use a "slice"

```python
my_list[1:3]
```

- You can think about a slice as `my_list[start:stop]`
    - **BUT**, note that the thing at `stop` is not included in the slice
    - another way to thing about it is `my_list[start : start + slice_length]`

### Slice from the beginning or to the end

```python
my_list[:3]
```

```python
my_list[2:]
```

### Modiying lists

Lists are "mutable", meaning we can change them.

```python
my_list[1] = 10
my_list
```
```python
my_list[1:3] = [1, 2, 3]
my_list
```

### A quick aside

Don't forget to google!

Eg. "How do I add something to a list in python?"

**Question 1**

Remove all of the strings from the list `my_list2`:

```python
my_list2 = ['a', 20, 2.3, 4.9, 'b', 7]
```

```py
# use this cell to figure out the code, then copy and paste it
# into the answer box in the quiz
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

### Dictionaries can be empty

```python
my_other_dict = {} # equivalent to `my_other_dict = dict()``
my_other_dict
```

And new elements can be added similar to assignment

```python
my_other_dict["key1"] = "value1"
my_other_dict["key2"] = "value2"
my_other_dict
```

Note that if you use the same key, you will override previous entries:

```python
my_other_dict["key1"] = "other value"
my_other_dict
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

### The order of key/value pairs does not matter

```python
dict2 = {
    "Bodhidharma" : 1,
    "César"       : 2,
    "Ada"         : 0,
    }
dict2 == my_dict
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

### As with other collections, sets can be empty...

```python
my_set = {}
my_set
```

```python
my_set.add('a')
my_set
```
```python
my_set.add('b')
my_set
```


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
        "lectures" : [3,4,7,9,10,12]
        }
    }

teaching_staff["Eric"]["e-mail"]
```

## Hands-on practice

**Write a loop that displays the square of every number from 0 to 10**

_NOTE: the last number displayed should be `100`_

```python
for ?? in ??: # replace the ??
    print()
```

The colors of the rainbow are often described as ROYGBIV
(red, orange, yellow, green, blue, indigo, violet)
corresponding to wavelengths between 650nm (red) and 400nm (violet).

**Make a dictionary where the names of the colors are the keys**
**and the wavelengths are the values**

Just make the wavelengths evenly spaced (how might you use math to let
python do this for you automatically?)

```python
color_dict = {
    "red" : 650,
    # enter other keys and valus here
    }
```

"Comprehensions" are syntax that let you generate collections using loops.
For example, compare the output of

```python
for i in range(5):
    print(i / 2)
```

to

```python
[i / 2 for i in range(5)]
```

**Use a list comprehension to make a list of all of the square of every number**
**from 0 to 10**

_the output should be `[0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100]`

```python
squares = [i for ?? in ??]
squares
```

Comprehensions can also be used to make sets and dictionaries.
For example, here's a dictionary comprehension:

```python
squares = {i : i ** 2 for i in range(5)}
squares
```
