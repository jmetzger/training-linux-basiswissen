# Create reposerver 

## Steps - on server 

```
dnf install -y httpd createrepo 
systemctl start httpd 
systemctl enable httpd 
cd /var/www/html
mkdir repo
cd repo 
dnf download lsof 
createrepo /var/www/html/repo 
```

```
# find public ip 
ip -br a
e.g. 61.41.41.12
```

## Steps: Test in browser

```
# Test in any browser 
http://61.41.41.12/repo
```

## Steps on clients to use repo 

```
dnf config-manager --add-repo http://61.41.41.12/repo
# Adjust some stuff 
cd /etc/yum.repos.d
mv [old-name.repo] company.repo
vi company.repo 
# change name in brackets to [company]
# add line 
gpgcheck=0 
```

```
# check if repo can be found under repolist
dnf repolist 
```

```
# see package with all destinations 
dnf list available lsof --showduplicates


# Install package on client from repo 
dnf install lsof --repo=company 

## Uuups: dependancy 
dnf install <depnendancy name>

## Try again 
dnf install lsof --repo=company 
```
