# ScanLine Function
Go-Language used to ScanLine function for default Scanner.<br>
The document of ScanLine function has the following description.<br>
<pre>
ScanLines is a split function for a Scanner that returns each line of text,
stripped of any trailing end-of-line marker.
The returned line may be empty.
The end-of-line marker is one optional carriage return followed by one mandatory newline.
In regular expression notation, it is `\r?\n`.
The last non-empty line of input will be returned even if it has no newline.
</pre>

There are two important points.

1. The return line may be empty.
	* It means it returns empty lines.
2. The last non-empty line of input will be returned even if it has no newline.
	* It means the last line of a file is always returned if it is non empty.
	* It does not mean however an empty line end the stream.

	
Finally, the scanner will stop on EOF(End Of File).<br>
Typing Ctrl-D for example will send end of file stop the scanner.


# References
* [Golang ScanLine Function](https://golang.org/pkg/bufio/#ScanLines)
* [Break out of input.Scan](http://stackoverflow.com/questions/34481065/break-out-of-input-scan)