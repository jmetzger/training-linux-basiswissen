# Grep Extended 

## Nach einzelenen Wort suchen (Wort muss so vorkommen) 

```
cat /etc/services | grep -i -w 'protocol'
```

## Eines der Begriffe soll vorkommen 

```
# Achtung, unbedingt -E für extended regex verwendet 
cat /etc/services | grep -E 'protocol|mysql' 
```

## Eines der Wort soll am Anfang der Zeile vorkommen 

```
# egrep ist das gleiche wie grep -E 
egrep  -i '^(mysql|Moira)' /etc/services
```


## Ref:

  * https://www.cyberciti.biz/faq/grep-regular-expressions/
