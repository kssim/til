# Regist insecure registry.
If you connect to the docker registry using an unauthenticated SSL certificate, the following error will occur.  

<pre>
x509: certificate signed by unknown authority  
</pre>  


To fix this error, you must register the registry with insecure-registry.  
If you do a web search, most of the ways to add insecure-registry to the DOCKER_OPTS option  
in "/etc/init.d/docker" or "/etc/default/docker" file.  
However, it does not work at all.  

Make a "/etc/docker/daemon.json" file and make the following settings, you need to restart the docker  
After that, you can access the docker registry using unauthorized SSL certificates.

<pre>
{
    "insecure-registries":["server1:port", "server2:port"]
}
</pre>  
