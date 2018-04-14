# Avoid float conversion automatically when division
When dividing an int value, **Python3** automatically converts to a float.  
In this case, if you divide the result into an int and work on it, you might get unintended results.  
The way to avoid this is simple. You can use the **"//"** operator instead of the **"/"** operator when dividing.  



## Example
### In Python3
```Python
>>> a = 1934168484684684848484848484848484884848848444444
>>> a
1934168484684684848484848484848484884848848444444
>>>
>>> a / 10
1.934168484684685e+47
>>>
>>> a // 10
193416848468468484848484848484848488484884844444
>>>
>>>
>>> a = 10
>>> a
10
>>>
>>> a / 10
1.0
>>>
>>> a // 10
1
```

### In Python2
```Python
>>> a = 1934168484684684848484848484848484884848848444444
>>> a
1934168484684684848484848484848484884848848444444L
>>>
>>> a / 10
193416848468468484848484848484848488484884844444L
>>>
>>> a // 10
193416848468468484848484848484848488484884844444L
>>>
>>>
>>> a = 10
>>> a
10
>>>
>>> a / 10
1
>>>
>>> a // 10
1
>>>
>>>
```
