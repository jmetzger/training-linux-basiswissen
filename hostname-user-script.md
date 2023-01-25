# Hostname - User - script.md 

```
cd /usr/local/sbin
nano manage.sh 
```

```
#!/bin/bash

USERNAME=$1
PASS=$2

if test -z $USERNAME
then
  echo You forgot to enter a username
  exit 1
fi

if test -z $PASS
then
  echo You forgot to enter a password
  exit 1
fi

COUNT=$(cat /etc/passwd | grep -c "^$USERNAME:")

if test $COUNT -eq 0
then
  echo User $USERNAME wird angelegt
  useradd -m -s /bin/bash $USERNAME
  usermod -aG sudo $USERNAME
  echo "$USERNAME:$PASS" | chpasswd
else
  echo User $USERNAME existiert bereits !
fi

hostnamectl set-hostname instructor.training.local

apt-get update -y
apt-get install -y apache2

exit 0
```

```
chmod u+x manage.sh 
manage.sh username passwort-des-users 
```
