# filetype plugin indent error?
Today I found the bug or error in vim configuration.<br>
I set the bellow option in my vimrc file, then 'expend tab' option is not worked.<br>
<code>filetype plugin indent on</code>

Suprisingly, it was not all that doesn't operate.<br>
Only python files did not work.<br>
For example, if you setted the bellow option in vimrc file, it was work.<br>
<code>au Bufenter *.\(c\) set expandtab</code>

But, if you setted the bellow option, it was not work.<br>
<code>au Bufenter *.\(py\) set expandtab</code>

Of course, bellow option was work, only in the files other than python.(*.py)<br>
<code>au Bufenter * set expandtab</code>

I wonder whether this is a bug in the vim option, but yet to find the exact cause.<br>
If I find out the cause, I'll update this file.<br>
If you ever knowing the cause, please open the issue.<br>

TIA :)