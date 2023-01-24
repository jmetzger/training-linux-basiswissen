# Apache als Proxy konfigurieren für tomcat

```
# Debian 
a2enmod proxy proxy_http

# Auf allen systemen 
systemctl restart apache2 
```



## VirtualHost konfiguration 

```
<VirtualHost *:80>
ServerAdmin root@localhost
ServerName myserversystem.mylabserver.com
DefaultType text/html
# Proxy aktivierierung 
ProxyRequests on
ProxyPreserveHost On
ProxyPass / http://localhost:8080/
ProxyPassReverse / http://localhost:8080/
</VirtualHost>

```
