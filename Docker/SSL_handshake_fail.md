# Connect Private Docker Registry Error.
When you try to connect the private docker registry server you can see the handshake fail message.  
If you see the following message, it's probably because you used the self-signed certificate as the IP address.  
  
<code>
Failed to tls handshake with x.x.x.x x509:

cannot validate certificate for x.x.x.x because it doesn't contain any IP SANs
</code>

To fix this error, you need to change the openssl configuration and recreate the certificate.  
Of course you have to work on the server in your private docker registry.  


First, go to the server where you want to create the certificate and modify the openssl.cnf file.  
(Enter the IP address to use for the IP address.)  

<pre>
[ v3_ca ]

subjectAltName = IP:x.x.x.x

</pre>

Next, re-create the certificate.  
The process of creating a certificate is omitted.  
Register the created certificate as an SSL certificate in the docker registry.

<pre>
ex)
docker run -d -p 5000:5000 --restart=always --name [NAME]   \
~~~
-e REGISTRY_HTTP_TLS_CERTIFICATE=[CERT FILE LOCATION].crt   \
-e REGISTRY_HTTP_TLS_KEY=[KEY FILE LOCATION].key   \
~~~
</pre>


Finally, restart the docker.  
So the above error will not be displayed.
