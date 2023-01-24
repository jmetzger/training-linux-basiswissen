# Less 

## Open a file with less 

```
# 
less /etc/services 

# Why ? 
# Leichtere Navigation 
```

## Pipen mit less (ausgabe an less schicken) 

```
ls -la | less 
cat /etc/services | less 
```

## Suchen in less 
```
#Innerhalb von less
/suchbegriff + RETURN
# nächstes Suchergebnis
n 
# voriges Suchergebnis 
N
```

## Rückwärts suchen in less 

```
#Innerhalb von less
?suchbegriff + RETURN
# nächstes Suchergebnis
n 
# voriges Suchergebnis 
N
```

##  Springen ans Ende/an den Anfang  
```
# Innerhalb von less
# ans Ende 
G 
# an den Anfang 
1g 
# zu einer bestimmten Zeile (Zeile 5)  
5g 
```

## In die Hilfe rein 

```
h 
# wieder raus
q
```
