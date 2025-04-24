# UCB_CS61A

## Lecture 2 Function

use "python3" in terminal to **start up** python

use "control + L" to clear

use "import" to import build-in names, build-in functions

``` python
from math import pi
from math import sin
```

"=" is the "assignment statement"

``` python
radius = 10
area, circ = pi * radius * radius, 2 * pi * radius
```

"assigment statement" can aslo be used to give names to functions

a "def statement" lets us create our own functions

``` python
from operator import add, mul
def square(x):
    return mul(x,x)
square(11)
# 121

radius
# 10
def area():
    return pi * radius * radius
area()
# 314.1592653589793
```

primitive expression : 2 (Number or Numeral) , add (name) , 'hello' (String)

call expression : max ( 2 , 3)

- "max" is **"operator"**
- "," is **"commas"**
- "2" and "3" are **"operand"**

an operand can also be an call expression

function definition is a more powerful means of abstraction : binds names to expressions

``` txt
>>> def <name> (<formal parameters>):
        return <return expression>
```

":" is called **"colon"**; tab is calld **"indent"**;

function **signature** indicates how many arguments a funtion takes

function **body** defines the computational process expressed by a function

Execution procedure for def statements

1. craete a function with signature \<name\>(\<formal parameters\>)
2. set the body of that function to be everything indented after the first line
3. bind \<name\> to that function in the current frame

Procedure for calling/applying user-defined functions(version1)

1. Add a local frame, forming a new environment
2. bind the function's formal parameters to its arguments in that frame
3. execuate the body of the function in that new environment

every expression is evaluated in the context of an environment

so far, the current environment is either:

- the global frame alone or,
- a local frame, followed by the global frame

**an environment is a sequence of frames (a frame is a binding between names and values)**

**a name evaluates to the value bound to that name in the earliest frame of the current environment in which that name is found**

- E.g. to look up some name in the body of the square function:
  - look for that name in the local frame
  - if not found. look for it in the global frame (build-in names like "max" are in the global frame too, but we don't draw them in environment diagrams)


---

## Lecture 3 Control

Every expression is evaluated in the context of an environment.

A name evaluates to the value bound to that name in the earliest frame of the current environment in which that frame is found.

"/" means true division

"//" means integer division, not including any remainder, is called "floordiv" in operator

```python
from operator import truediv, floordiv
```

"%" is mud operator, it give the remainder of devision

```python
from operator import mod
```

python can also return multiple values from a function

```python
>>> def dived_exact(n, d):
...     return n // d, n % d
...
>>> a, b = dived_exact(123, 10)
>>> a
12
>>> b
3
>>>
```

using "-i" option can run python 3 in the "interactive mode"

```python
python3 -i test_python.py
hello, python
>>>
```

Using "-m dockets" option can stimulate the example interactive session in the .py file

```python
def divied_exact(N, D):
    '''Return the quotient and remainder of dividing N by D

    >>> q, r = divied_exact(123, 10)
    >>> q
    12
    >>> r
    3
    '''
    return N // D, N % D
```

```shell
python3 -m doctest test_python.py
```

If everything does what it's supposed to do, there's no output. 

Using "-v" option can show more detailes

```shell
➜  test python3 -m doctest -v test_python.py
Trying:
    q, r = divied_exact(123, 10)
Expecting nothing
ok
Trying:
    q
Expecting:
    12
ok
Trying:
    r
Expecting:
    3
ok
1 items had no tests:
    test_python
1 items passed all tests:
   3 tests in test_python.divied_exact
3 tests in 2 items.
3 passed and 0 failed.
Test passed.
```

When definding a function, you can give a default value

```python
def divied_exact(N, D = 10):
    return N // D, N % D
```

A statement is executed by the interpreter to perform an action

A clause is a single header followed by some indented statements, and those indented statements are called the suit of the clause.

### **Conditional Statements**

- Always starts with "if" clause 
- Zero or more "elif" clause
- Zero or one "else" clause, always at the end

```python
def absolute_value(x):
    '''Return the absolute value of x

    >>> r = absolute_value(-2)
    >>> r
    2
    '''
    if x < 0:
        return -x
    elif x == 0:
        return 0
    else:
        return x
```

**False values in Python: False, 0, '', None  (more to come)**

**True values in Python: Anything else**

### **Iteration**

A while statement is a compound statement that contains within its body something that we want to execute multiple times

**Execution Rule for While Statement:**

1. Evaluate the header's expression

2. If it is a true value, execute the whole suite, then return to step 1

```python
>>> i, total = 0, 0
>>> while i < 3:
...     i = i + 1
...     total = total + i
...
>>> i
3
>>> total
6
>>>
```

