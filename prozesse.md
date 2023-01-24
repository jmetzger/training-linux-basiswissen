# Prozesse 

## Prozesse anzeigen 

```
ps -ef 
ps aux  # x alle Prozesse anzeigen, die nicht an ein Terminal gebunden sind 
```

## Bestimmte Prozesse anzeigen mit Kopfzeile 

```
ps -ef | head -n 1; ps -ef | grep ssh 
```

## systemctl (läuft Dienst) 

```
systemctl status sshd 

```

## Prozeßbaum anzeigen (meist nicht für die Praxis notwendig) 

```
pstree -p 
```
