# NULL character
In Linux, it expressed as a null character '^@'. Mostly you can see when you open a file in the proc to vi or any other editor.

Use the 'cat' null character is omitted.
but, give the '-A' option can be viewed as shown in the editor.

<pre>
# cat /proc/408/cmdline
/usr/sbin/cron-f%
#
# cat -A /proc/408/cmdline
/usr/sbin/cron^@-f^@%
</pre>


To change the null characters with spaces, use the 'tr' command.

<pre>
# tr -s '\0' < /proc/408/cmdline | tr '\0' ' '
/usr/sbin/cron -f %
</pre>


If you want to change in Python or other scripting languages are as follows:

```python
f.readline().replace('\0', ' ')
```