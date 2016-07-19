# RPM DB Broken
If you have typed the command 'rpm -qa' and comes out the following message, it would have broken RPM DB.

<pre>
# rpm -qa
rpmdb: PANIC: fatal region error detected; run recovery
error: db4 error(-30974) from dbenv->open: DB_RUNRECOVERY: Fatal error, run database recovery
error: cannot open Packages index using db3 - (-30974)
error: cannot open Packages database in /var/lib/rpm
</pre>

In this case, it will recover by deleting the existing db files and perform a rebuild.

<pre>
rm -rf /var/lib/rpm/__db*
rpm —rebuilddb
</pre>