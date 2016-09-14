# Force division to be floating point
##1. Upgrade to Python3
In Python 3, to get true divison, you simply do <code>a / b</code>.

```Python
>>> 1 / 2
0.5
```

##2. Using Python2
In Python 2, it's not so simle. Some ways of dealing with classic Python 2 division are better and more robut than others.

###1. Recommanded
You can get Python 3 division behavior in any given module with the following import at the top:

```Python
from __future__ import division
```

which then applies Python 3 style division to the entire module. It also works in a python shell at any given point.

```Python
>>> from __future__ import division
>>> 1 / 2
0.5
```


###2. Other Options
If you don't want to apply this to the entire module, you're limited to a few workarounds. The most popular is to corece one of the operands to a float. One robust solution is <code>a / (b * 1.0)</code>. In a fresh Python shell:

```Python
>>> 1 / (2 * 1.0)
0.5
```

Also robust is <code>truediv</code> from the <code>operator</code>module <code>operator.truediv(a,b)</code>, but this is likely slower because it's a function call:

```Python
>>> from operator import truediv
>>> truediv(1, 2)
0.5
```


###3. Not recommended
Commonly seen is <code>a / float(b)</code>. This will raise a TypeError if b is a complex number. Since division with complex numbers is defined, it makes sense to me not have division fail when passed a complex number for the divisor.

```Python
>>> 1 / float(2)
0.5
>>> 1 / float(2j)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can't convert complex to float
```


It doesn't make much sense to me to purposefully make your code more brittle.


You can also run Python with the -Qnew flag, but this has the downside of executing all modules with the new Python 3 behavior, and some of your modules may expect classic division, so this is not recommended. But to demonstrate:

```Shell
$ python -Qnew -c 'print 1/2'
0.5
$ python -Qnew -c 'print 1/2j'
-0.5j
```


# References
[How can I force division to be floating point in Python?](http://stackoverflow.com/questions/1267869/how-can-i-force-division-to-be-floating-point-in-python)