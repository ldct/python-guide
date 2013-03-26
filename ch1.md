## Introduction

Hi. This is a guide to python for programmers. We shall be using Python 3.

Some conventions - the ``>>>`` symbol means we type something directly into the interpreter, which generally echoes back the result (thus saving us from unnecessary ``print`` commands).

```python
>>> 1 + 2 + 3
6
```

## Numeric

There are three built-in numeric types - ``int``, ``float`` and ``complex`` [Docs: [4.4 Numeric Types] (http://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)]

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
