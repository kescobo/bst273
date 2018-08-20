# Lecture 03 - Variables, Scalars and Functions

2018-09-11
Kevin Bonham, PhD

## Outline

- Meaning vs syntax
- Variables and methods
- `Type`s of information (scalars)
- **Hands-on**: working with variables and functions

## Learning Ojectives

At the end of this class period, you should be able to:
1. Identify and explain the difference between common scalar types
2. Create and modify variables in python
3. Perform basic arithmetic calculations in code
4. Manipulate strings and print the results to the console

## Meaning vs Syntax

- A programming "language" is really a translation
  - Human intent --> machine code
- There are two basic features in any language:
  - Data (information)
  - Instructions (actions)

### The type of translation between intent and machine code is the "syntax"

For example to ask the computer to display some text on the screen...

In python 2: `print "Hello, World!"`
In python 3: `print("Hello, World!")`
In julia: `println("Hello, World!")`
In java: `System.out.println("Hello, World!")`

### We will be using python3 syntax

But many (most?) of the concepts you learn in this course
are applicable to other languages too.
Just append `in {LANGUAGE}` to your google search to learn the syntax. Eg:

```python
for language in ['python 2', 'python 3', 'julia', 'java', 'ruby', 'perl']:
    print('How do I print something to the screen in {}?'.format(language))
```

###

## Variables store information

```python
2 + 2
```
```python
x = 42
```
```python
x
```
```python
x + 2
```
