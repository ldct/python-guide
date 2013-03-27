## Introduction

Hi. This is a guide to Python 3. It is intended to be read by people who are already fluent in another programming language.

I intend for it to be a hybrid between a manual and a tutorial. It will have as few forward dependencies as possible. It is not meant to be comprehensive, but will cover about 95% of the language that a working pythonista uses. However, we will try to be rigorous and keep the hand-wavingness found in introductory tutorials to a minimum.

This chapter will cover enough of numerics and lists to introduce functional programming in python.

Some conventions - the ``>>>`` symbol means we type something directly into the interpreter, which generally echoes back the result (thus saving us from unnecessary ``print`` commands).

```python
>>> 1 + 2 + 3
6
```

Also, [doc: [link](http://docs.python.org/3/)] will be used to refer to the official python documentation.

## Numeric

There are three built-in numeric types - ``int``, ``float`` and ``complex`` [doc: [4.4 Numeric Types] (http://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)]. Complex numbers will not be covered here. 

```python
>>> 1 + 2 + (3 * 4) 
15
>>> 3 / 2
1.5
>>> 1 + 2.5
3.5
```

The last two examples illustrate a general principles - ``int``s will upconvert to ``float``s on demand. In fact ``/`` is the floating-point divison operator, which means that even exact division always produces floats. 

When two numbers are compared, a boolean (the special values ``True`` and ``False``) is produced. Numbers will be up-converted as necessary

```python
>>> 3 > 3.0
False
>>> 3 >= 3.0
True
```

### Modular arithmetic and rounding

The built-in ``int`` function can be used to convert floats to ints.

```python
>>>  6 / 2
3.0
>>> int(3.0)
3
```

Another way would be to use the ``//`` operator. 

```python
>>> 6 // 2
3
>>> 5 // 2
2
```

Note that ``int`` rounds to zero while ``//`` rounds to negative infinity. 

```python
>>> -5 // 3
-2
>>> -(5 // 3)
-1
>>> int(-5/3)
-1
```

This strange behaviour is needed to make the definition of the modulo operator ``%`` make sense.

## Functions

Python reserves two keywords, ``def`` and ``return``, for functions. ``def`` starts a function definition, with the arguments listed in brackets

```python
def square(x):
  return x*x
```


Functions can be defined within other functions, and first-class functions are supported.

```python
def compose(f,g):
  def h(x):
    return f(g(x))
  return h
  
>>> compose(square,square)
<function h at 0x100dc88>

>>> compose(square,square)(2)
16
```


## Lists

Lists are one of the most commonly used data structures in python.

```python
>>> l = [1,2,3,4]
>>> len(l)
4
>>> l[0]
1
>>> l[-1]
4
```

As can be seen, the standard ``l[i]`` notation is used to access the ith element of the list, with the head having index 0. Negative indices count from the back.

However, python also extends this syntax, using ``l[i:j]`` to specify the sublist from ``i`` inclusive to ``j`` exclusive. If any of them are ommitted, the slice is continued until the end of the list.

```python
>>> l[1:3]
[2,3]
>>> l[1:]
[2,3,4]
>>> l[:]
[1,2,3,4]
```

The third argument is a step argument

```python
>>> l[::2]
[1,3]
>>> l[::-1]
[4,3,2,1]
```

The `+` operator is used to concatenate lists

```python
>>> [1,2] + [3]
[1,2,3]
```

## Command line arguments

Python uses the the name ``argv`` to denote the list of program arguments. As there is a built-in ``len`` function, ``argc`` is not needed. ``argv`` must be imported from ``sys``:

```python
import sys
print(sys.argv)
```
