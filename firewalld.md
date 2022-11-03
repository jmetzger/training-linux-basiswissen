# firewalld (ubuntu 20.04)  

## Install firewalld and restrict ufw 

```
# Schritt 1: ufw deaktivieren 
systemctl stop ufw
systemctl disable ufw 
ufw disable # zur Sicherheit 
ufw status
# -> disabled # this has to be the case 
```

```
# Schritt 2: firewalld 
apt install firewalld 
systemctl status firewalld 

# doublecheck ufw 
systemctl status ufw 

```


## Is firewalld running ?
```
# is it set to enabled ?
systemctl status firewalld 
firewall-cmd --state
```

## Command to control firewalld 
  
  * firewall-cmd 



## Zones documentation 

man firewalld.zones 

## Zones available 

```
firewall-cmd --get-zones 
block dmz drop external home internal public trusted work
```

## Active Zones 

```
firewall-cmd --get-active-zones
# in our case empty 
```

## Add Interface to Zone = Active Zone 

```
firewall-cmd --zone=public --add-interface=enp0s3 --permanent 
firewall-cmd --reload 
firewall-cmd --get-active-zones 
public
  interfaces: enp0s3

```

## Show information about all zones that are used 
```
firewall-cmd --list-all 
firewall-cmd --list-all-zones 
```


## Default Zone 

```
# if not specifically mentioned when using firewall-cmd
# .. add things to this zone 
firewall-cmd --get-default-zone
public
```

## Show services / Info
```
firewall-cmd --get-services 
firewall-cmd --info-service=http
```

## Adding/Removing a service 

```
# Version 1 - more practical 
# set in runtime 
firewall-cmd --zone=public --add-service=http
firewall-cmd --runtime-to-permanent 

# Version 2 - less practical
firewall-cmd --permanent --zone=public --add-service=http
firewall-cmd --reload 
```

```
## Service wieder entfernen
firewall-cmd --permanent --zone=public --remove-service=ssh
firewall-cmd --reload 
```

## Best way to add a new rule 
```
# Step1: do it persistent -> written to disk 
firewall-cmd --add-port=82/tcp --permanent  

# Step 2: + reload firewall 
firewall-cmd --reload 
```

## Enable / Disabled icmp 
```
firewall-cmd --get-icmptypes
# none present yet 
firewall-cmd --zone=public --add-icmp-block-inversion --permanent
firewall-cmd --reload
```

## Working with rich rules 
```
# Documentation 
# man firewalld.richlanguage

# throttle connectons 
firewall-cmd --permanent --zone=public --add-rich-rule='rule family=ipv4 source address=10.0.50.10/32 service name=http log level=notice prefix="firewalld rich rule INFO:   " limit value="100/h" accept' 
firewall-cmd --reload # 
firewall-cmd --zone=public --list-all

# port forwarding 
firewall-cmd --get-active-zones
firewall-cmd --zone=public --list-all
firewall-cmd --permanent --zone=public --add-rich-rule='rule family=ipv4 source address=10.0.50.10 forward-port port=42343 protocol=tcp to-port=22'
firewall-cmd --reload 
firewall-cmd --zone=public --list-all
firewall-cmd --remove-service=ssh --zone=public

# 


# list only the rich rules 
firewall-cmd --zone=public --list-rich-rules

# persist all runtime rules 
firewall-cmd --runtime-to-permanent

```


## References 

  * https://www.linuxjournal.com/content/understanding-firewalld-multi-zone-configurations#:~:text=Going%20line%20by%20line%20through,or%20source%20associated%20with%20it.
  * https://www.answertopia.com/ubuntu/basic-ubuntu-firewall-configuration-with-firewalld/
