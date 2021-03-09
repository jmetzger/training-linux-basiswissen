# Grub konfigurieren

## Walkthrough 

```
# Step 1
# z.B. timeout hochsetzen, wie lange er mit Booten im Bootmenu wartet
cd /etc/default
vi grub 
##  make wanted changes 
#GRUB_TIMEOUT_STYLE=hidden
GRUB_TIMEOUT=5

# Step 2
update-grub 

# Step 3 - reboot 

# When grub menu appears enter arrow-down arrow-up ONCE 
# Dann zählt er nicht weiter runter und bootmenu bleibt stehen. 

# Mit e kann man einen boot-eintrag für den nächsten Boot ändern 

# Ändern und dann CTRL bzw. STRG + x für das Booten nach Änderung 

# Step 4 - be happy 
```
