# Hourly - Cronjob einrichten 

## Walkthrough 

```
cd /etc/cron.hourly 
# nano datum
# wichtig ohne Endung 
# Job wird dann um 17 nach ausgeführt ? 

###

#!/bin/bash
date >> /var/log/datum.log

chmod 755 datum  # es müssen x-Rechte (Ausführungsrechte gesetzt sein) 

## Abwarten, Tee trinken 
```
 
