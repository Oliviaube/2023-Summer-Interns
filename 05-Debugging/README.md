# Debugging Python and a JupyterLab Notebook
## Assumptions
The concept of debugging is about assumptions. You have made an assumption about how a program, a language or algorithm works, and that assumption is not correct. What can complicate things, is that the compiler/interpreter will provide a message to you, based on assumptions as well. Frequently, the latter assumption will be incorrect as to solving the former assumption.


When faced with an error, don't make the third assumption...that your code is wrong and the compiler is correct. Generally, the less experienced the programmer, the lower the chance the compiler is making the right assumption.

## What to do
We've arrived at point, where you might say *"Now what?"*

To resolve these assumptions, its best to explicitly determine what is happening in your program. Advanced programmers will use debuggers such as those embedded in *VS Code* or a tool such as *gdb* (*gnu debugger*). When you are starting out, understanding how a debugger works, and how to use it well, will make solving errors more difficult. In our case, we will be using *print* statements. 

The ideal format of a *Python* print statement is the f-string print. This provides a easy method to identify the variable and provide additional text as desired. A simple example is:
```python
print(f"{var=}")
```

Where var is replaced by the name of the variable in question.

## Commands to Consider
### print() to show value
As stated before, the first approach would be the simplest:
```python
print(f"{var=}")
```
Use a print statement to see the value of the variable at the specific point of the program failing.

### print(type()) to show variable type
If the compiler is showing a type error such as `can't multiply sequence by non-int of type 'str'` than it can be helpful to show the type of the variable as compared to its value:
```python
print(f"{type(var)=}")
```

### Print a list or dictionary
As soon as an error occurs with a list or dictionary, be sure to print it. The command is the same as printing a variable, however, you will see all of the values. If you are attempting to raise the power of a variable by another variable and a list of values shows up, that is the source of your error.

```python
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
Cell In[5], line 3
      1 alist = [1, 2, 3, 4]
      2 print(f"{alist=}")
----> 3 total = alist ** 2

TypeError: unsupported operand type(s) for ** or pow(): 'list' and 'int'
```

### Print(dir()) to show functions available
Sometimes you are attempting to use a function, however, its mis-spelled. An easy way to see the available functions of a particular library is to use `dir(library)`. This will print out the available functions.
```python
---------------------------------------------------------------------------
AttributeError                            Traceback (most recent call last)
Cell In[14], line 2
      1 import statistics
----> 2 print(statistics.stddev(alist))

AttributeError: module 'statistics' has no attribute 'stddev'

import statistics
# print(stddev(alist))
print(dir(statistics))
['Counter', 'Decimal', 'Fraction', 'NormalDist', 'StatisticsError', '__all__', '__builtins__', '__cached__', '__doc__', '__file__', '__loader__', '__name__', '__package__', '__spec__', '_coerce', '_convert', '_exact_ratio', '_fail_neg', '_find_lteq', '_find_rteq', '_isfinite', '_normal_dist_inv_cdf', '_ss', '_sum', 'bisect_left', 'bisect_right', 'erf', 'exp', 'fabs', 'fmean', 'fsum', 'geometric_mean', 'groupby', 'harmonic_mean', 'hypot', 'itemgetter', 'log', 'math', 'mean', 'median', 'median_grouped', 'median_high', 'median_low', 'mode', 'multimode', 'numbers', 'pstdev', 'pvariance', 'quantiles', 'random', 'sqrt', 'stdev', 'tau', 'variance']

import statistics
print(statistics.stdev(alist))
1.2909944487358056
```
