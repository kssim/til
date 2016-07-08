# Code convention
When cooperative work with others, it is important to define the code convention.
Among them, I'm going to talk a tab-space issues today.

In the case of where I work, we use the tab in the source code(Even it is scripts!!!). In fact, I didn't care to use the tab, because it is convenient for me.

But!!! Now I changed my thinking.
Referring to PEP8 or Google Code Convention can be seen that the number of people using the space.
So I decided to change the tab to all the existing code space.

In this file, I'll be talking about how to change the tab to space using vim settings.

# Vim Configuration
* The following settings in the '.vimrc' file.
	* ".vimrc" file is in the "~/.vimrc"

```bash
set tabstop=4					# or ts
au Bufenter * set expandtab		# or et
```

* If you want to change the existing file automatically, open the file and use the following command:
	* <code>:retab</code>
