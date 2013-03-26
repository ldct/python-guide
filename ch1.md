## Introduction

Hi. This is a guide to Python 3.

It is intended to be read by people who are already fluent in another programming language.

I intend for it to be a hybrid between a manual and a tutorial. It will have as few forward dependencies as possible. It is not meant to be comprehensive, but will cover about 95% of the language that a working pythonista uses. However, we will try to be rigorous and keep the hand-wavingness found in introductory tutorials to a minimum.

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

The last two examples illustrate a general principles - ``int``s will upconvert to ``float``s on demand. In fact ``/`` is the floating-point divison operator, which means that even exact division always produces floats. The built-in ``int`` function can be used to convert them back.

```python
>>>  6 / 2
3.0
>>> int(3.0)
3
```

Lists
---

Lists are one of the most commonly used data structures in python.
```python
l = [1,2,3]
len(l)
```


Command line arguments
---

Python uses the the name ``argv`` to denote the list of program arguments. As there is a built-in ``len`` function, ``argc`` is not needed. ``argv`` must be imported from ``sys``:

```python
import sys
print(sys.argv)
```
