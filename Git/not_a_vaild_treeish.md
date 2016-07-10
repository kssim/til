# Build Error
When you try to build using the git-buildpackage command sometimes can occur the following erorr.

<code>gbp:error: upstream/x.x.x is not a valid treeish</code>

This error occurs because it is not specified in the source tree for the debian source code.
And this error occurs only when you get checked out first build the source code.

Use the following options can be built.
Once again the building can be built without options.

<code>git-buildpackage -us -uc --git-upstream-tree=[your branch name]</code>

However, to avoid fundamental errors like that. Just add the following settings in "debian/gbp.conf" file.

<pre>upstream-tree = [your branch name]</pre>

<pre>
ex)
[DEFAULT]
upstream-branch = [your branch name]
debian-branch = [your branch name]
upstream-tree = [your branch name]
</pre>


# In my case
I found the above problem when you build from the debian 8.
However, there was no problem in the debian 6 and debian 7 the same code. So I first discovered the problem and had a lot of embarrassment. **I realized on the above example that if you work in a variety of environments, preference is important.**