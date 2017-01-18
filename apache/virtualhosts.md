# Virtualhosts on Apache server

## Domain
First You need to configure domain name on DNS server which will be pointing to the server hosting Yor Virtualhosts.

## Simple HTML page on Apache
```
<VirtualHost *:80>
    ServerAdmin admin@server.com
    ServerName your.domain.name.com
    DocumentRoot "/var/www/path/to/your/page"
</VirtualHost>
```

## Application server via HTTP (WebRick)
```
<VirtualHost *:80>
    ServerAdmin admin@server.com
    ServerName your.domain.name.com
    
    ProxyPreserveHost On
    ProxyPass / http://localhost:3000/
    ProxyPassReverse / http://localhost:3000/
</VirtualHost>
```

## Java application server via AJP (Tomcat)
```
VirtualHost *:80>
   ServerAdmin admin@server.com
   ServerName your.domain.name.com
   ErrorLog /var/log/apache2/ajp.error.log
   CustomLog /var/log/apache2/ajp.log combined

   <Proxy *>
     AddDefaultCharset Off
     Order deny,allow
     Allow from all
   </Proxy>

   ProxyPass / ajp://localhost:8009/
   ProxyPassReverse / ajp://localhost:8009/
</VirtualHost>

```