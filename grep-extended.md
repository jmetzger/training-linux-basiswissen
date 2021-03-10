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


## Ref:

  * https://www.cyberciti.biz/faq/grep-regular-expressions/
