# Compare Input and readline.
Today I try to use a <code>parse\_and\_bind</code> function in readline modules.
But, I fail to use that function. Because my program use a <code>sys.stdin.readline()</code> function, it does not support functions in readline module.
So I change the <code>readline()</code> function to <code>raw_input()</code> function.
Then, it is worked. So I wrote the differences between the two functions.


## input() / raw_input()
* It takes an optional prompt argument.
* It also strips the trailing newline character from the string it returns.
* It support history if the [readline](https://docs.python.org/3/library/readline.html#module-readline) module is loaded.
* It support functions of [readline](https://docs.python.org/3/library/readline.html#module-readline) module.
	* such as, <code>parse\_and\_bind</code> or <code>set\_completer</code> function.


## readline() / sys.stdin.readline()
* It takes an optional size argument.
* It does not strip the trailing newline character.
* It does not support history whatever.
* It does not support functions of [readline](https://docs.python.org/3/library/readline.html#module-readline) modules.


# References
* [PEP-3111](https://www.python.org/dev/peps/pep-3111/)
* [Reading a line from standard input in python](http://stackoverflow.com/questions/6966194/reading-a-line-from-standard-input-in-python)