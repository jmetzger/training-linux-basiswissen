# Gegenüberstellung systemctl / /etc/init.d / service 

```
SySV

a) /etc/init.d/rsyslog status 
/etc/init.d/rsyslog start
/etc/init.d/rsyslog status

b) service rsyslog 

Systemd 

# geht auch (unter der Haube wird systemctl verwendet) 
service rsyslog status 


```
