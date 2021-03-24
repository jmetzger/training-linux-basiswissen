# IP-Adresse von DHCP-Server holen

## Walkthrough 

```
# Ip nicht gesetzt - kurzfristig eine IP holen
ip a # zeigt die Netzwerkschnittstellen an.
dhclient enp0s8 # ip - Adresse für Schnittstelle enp0s8 holen  
ip a
```
