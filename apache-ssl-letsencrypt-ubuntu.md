# Apache SSL with letsencrypt ssl 

## Step 1:

```
# prerequisite - apache runs already 
sudo apt update 
sudo apt install -y certbot python3-certbot-apache
```

## Step 2: checking virtualhost comfiguration

```
sudo nano /etc/apache2/sites-available/projekt1-training-local.conf

```



## Attention: virtual host - domain must be different than hostname 

```
e.g. ap1.t3isp.de (virtual host domain) != hostname 
# if this is not the case change hostname
hostnamectl set-hostname main.training.local 

# be sure to restart apache to take 
systemctl restart httpd 

```


## Step 3: Use certbot to configure 

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
  
