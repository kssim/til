# MRO
MRO is the abbreviation of Method Resolution Order.<br>
MRO it the order in which base classes are searched when looking for a method.<br>
In Python this also applies to other attributes.<br>
<br>
Python has known at least three different MRO algorithms:<br>
classic, Python2.2 new-style, and Python2.3 new-style (a.k.a.C3).<br>
Only the latter survives in Python3.<br>


# Examples
```Python
class First(object):
    ...
    
class Second(object):
    ...

class Third(First, Second):
    def __init__(self):
        super(Third, self).__init__()
```
In above case, the MRO would be [Third, First, Second].
<br>
<br>

```Python
class First(object):
    ...
    
class Second(First):
    ...

class Third(First):
    ...
    
class Fourth(Second, Third):
    def __init__(self):
        super(Fourth, self).__init__()
```
In above case, the MRO would be [Fourth, Second, Third, First].
<br>
<br>

```Python
class First(object):
    ...
    
class Second(First):
    ...

class Third(First, Second):
    def __init__(self):
        super(Third, self).__init__()
```
In above case, there's no obvious expectation, and Python will raise an error.

<pre>
TypeError: Error when calling the metaclass bases Cannot create a consistent 
method resolution order (MRO) for bases Second, First
</pre>

<br>

Super basically picks one(or all) of its parents in a specific order.
If you only want to call a single parent's method, do this.

```Python
class Third(First, Second):
    def __init__(self):
        First.__init__(self)
```


# References
* [Method Resolution Order - Guido's Blog](http://python-history.blogspot.kr/2010/06/method-resolution-order.html)
* [C3 linearization - Wiki](https://en.wikipedia.org/wiki/C3_linearization)