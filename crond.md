# Cronjob (Zentral) 

```
cd /etc/cron.d 
## cronjob anlegen
# Achtung: ohne Dateiendung 
# ls -la trainingscript
# root@ubuntu2004-104:/etc/cron.d# ls -la trainingscript
# -rw-r--r-- 1 root root 471 Mar 26 12:44 trainingscript

# cat trainingscript
SHELL=/bin/sh
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin

# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  * user-name command to be executed
*/2  *  *  *  * root  /root/script.sh


## Script anlegen 
cat script.sh
#!/bin/bash
TAG='FREITAG'
echo " ---- " >> /var/log/scripting.log
date >> /var/log/scripting.log
echo $TAG >> /var/log/scripting.log

## Script - Berechtigungen setzten 
chmod u+x /root/script.sh 

## Scriptausführung  testen 
## trägt es etwas im Log ein -> /var/log/scripting.log 
/root/script.sh


#### Warten 


## nach 2 Minuten log betrachten 
ls -la /var/log/scripting.log 

## cron daemon braucht nicht reloaded zu werden 


```
