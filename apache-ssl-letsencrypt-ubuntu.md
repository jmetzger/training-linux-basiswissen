# Apache SSL with letsencrypt ssl 

## Step 0:

```
# prerequisite - apache runs already 
apt update 
sudo apt install certbot python3-certbot-apache
```

## Step 1: checking virtualhost comfiguration

```
sudo nano /etc/apache2/sites-available/your_domain.conf

```

```
#  x = 1 to 7
#  apx.t3isp.de 
#  mx.t3isp.de
# mkdir /etc/httpd/sites-enabled
# cd /etc/httpd/sites-enabled 
# vi ap1.t3isp.de.conf 
<VirtualHost *:80>
    ServerName www.ap1.t3isp.de
    ServerAlias ap1.t3isp.de
    DocumentRoot /var/www/ap1.t3isp.de/html
    ErrorLog /var/log/httpd/ap1-t3isp-de-error.log
    CustomLog /var/log/httpd/ap1-t3isp-de-access.log combined
</VirtualHost>
```

```
/var/www
mkdir -p ap1.t3isp.de/html
cd ap1.t3isp.de/html/
echo "ich bin ap1 von jochen" > index.html
```

## Variant 1: Attention: virtual host - domain must be different than hostname 

```
e.g. ap1.t3isp.de (virtual host domain) != hostname 
# if this is not the case change hostname
hostnamectl set-hostname main.training.local 

# be sure to restart apache to take 
systemctl restart httpd 

```

## Variant 2: Remove <VirtualHost> </VirtualHost> - block vom ssl.conf 

```
# ssl.conf - Created by installation of mod_ssl. 
cd /etc/httpd/conf.d/
# vi ssl.conf 
remove
<VirtualHost>
....
</VirtualHost>

systemctl restart httpd 

```

## Use certbot to configure 

```
certbot --apache --register-unsafely-without-email 
```

## Test with your browser 

```
https://ap1.t3isp.de 

```

## Test Certificate with ssl labs 

  * https://ssllabs.com

## Refs:

  * https://www.digitalocean.com/community/tutorials/how-to-secure-apache-with-let-s-encrypt-on-ubuntu-22-04
  
