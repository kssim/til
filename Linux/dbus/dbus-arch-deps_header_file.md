# Problem
When you build a dbus-related libraries sometimes encounter the following error.

<pre>
/usr/include/dbus-1.0/dbus/dbus.h:29:33: fatal error: dbus/dbus-arch-deps.h: No such file or directory
</pre>


# Reason
This error occurs not find the path to the <code>dbus/dbus-arch/deps.h</code> file.
This header file is located in <code>/usr/lib/<architecture>/dbus-1.0/include/</code>.


# Solution
Find path and fix makefile. Find the path using pkg-config command. If you find the path, add the path to the makefile.

```bash
# pkg-config dbus-1 --cflags
-I/usr/include/dbus-1.0 -I/usr/lib/x86_64-linux-gnu/dbus-1.0/include
```
