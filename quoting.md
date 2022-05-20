# Quoting 

## Beispiel 1:
```
DATUM=$(date)
root@ubuntu2004:~# echo "Das ist das heutige $DATUM"
Das ist das heutige Do 19. Mai 13:50:07 CEST 2022
root@ubuntu2004:~# echo 'Das ist das heutige $DATUM'
Das ist das heutige $DATUM

# Verschiedene Quotes nacheinander 
echo "Das ist's:"'Das ist das heutige $DATUM'


```

## Mehrzeiliges Beispiel 

```
Mehrzeilges Beispiel 
echo 'hallo
> das geht so
> .. oder auch icht'
hallo
das geht so
.. oder auch icht
```

## Hochkommas verwenden 

```
# Einfache gehen nur ausserhalb
echo 'Test'\'' so geht es weiter'
# oder mit $ 
echo $'Test\' so geht es weiter'


echo "\"Ein Sprichwort\""
# oder
echo '"Ein Sprichtwort"' 

```
