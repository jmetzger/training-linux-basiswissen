# UFW 

## Läuft der Dienst für die Firewall 

```
systemctl status ufw 
```

## Ist die Firewall scharfgeschaltet ? 

```
ufw status
```

## Firewall aktivieren (Achtung ssh) 

```
# Neue ssh - Verbindungen werden nicht angenommen 
# Bestehende Bedingungen (ESTABLISHED) bleiben erhalten 
ufw enable 
ufw status 
```

## Port hinzufügen 

```
ufw allow 22 # for tcp and udp
# or 
ufw allow ssh # uses /etc/services for detection of port - number
ufw status 
```
