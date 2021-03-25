# rsyslog 

## Alle Logs an zentralen Log-Server schicken


```
/etc/rsyslog.conf
# udp 
*.*  @192.168.10.254:514
# tcp 
*.*  @@192.168.10.254:514

Ref: https://www.tecmint.com/setup-rsyslog-client-to-send-logs-to-rsyslog-server-in-centos-7/
```
