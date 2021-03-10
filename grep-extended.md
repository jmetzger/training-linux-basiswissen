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

## x-Zeilen vor bzw. nach "Finde-(Grep-)"  - Ergebnis anzeigen

```
# -A x-Zeilen danach, z.B. -A 4 --> 4 Zeilen danach 
# -B x-Zeilen davor 
egrep  -A 4 -B 4 -i '^(mysql|Moira)' /etc/services'^(mysql|Moira)' /etc/services
```

## Einzelne Zeichen als Suchmuster nehmen 

```
# 0, dann zwei beliebige Zeichen, dann tcp 
grep '0..tcp' /etc/services
# 0, dann ein beliebiges Zeichen, dann tcp 
grep '0.tcp' /etc/services 

```

## Tatsächlich eine Punkt suchen 

```
# /root/dateinamen 
hans.txt 
hans1txt
peter.txt

grep 'hans\.txt' /root/dateinamen 

root@ubuntu2004-101:/etc# grep 'hans\.txt' /root/dateinamen
hans.txt
root@ubuntu2004-101:/etc# grep 'hans.txt' /root/dateinamen
hans.txt
hans1txt



```

## Einzelne Zeichen sollen vorkommen 

```
root@ubuntu2004-101:~# echo "Klaus" >> /root/namen
root@ubuntu2004-101:~# echo "klaus" >> /root/namen
root@ubuntu2004-101:~# grep '[kK]l' /root/namen
Klaus
klaus
root@ubuntu2004-101:~# grep '[kK][la]' /root/namen
Klaus
klaus
root@ubuntu2004-101:~# echo "karin" >> /root/namen
root@ubuntu2004-101:~# grep '[kK][la]' /root/namen
Klaus
klaus
karin
```

```
echo "Klaus1" >> /root/namen
root@ubuntu2004-101:~# echo "Klaus2" >> /root/namen
root@ubuntu2004-101:~# grep '[kK][la]aus[0-9]' /root/namen
```

## Mengeangabe 

```
# Achtung unbedingt egrep oder grep -E verwenden 
cat /root/namen
AxB nix
AxB nix
abc nix
a nix

egrep '^[a-zA-Z]{1,3} nix' /root/namen
```

```
echo "ab nix" >> /root/namen
# Mindestens 2 Zeichen 
root@ubuntu2004-101:~# egrep '^[a-zA-Z]{2,} nix' /root/namen
AxB nix
AxB nix
abc nix
ab nix
```

## Nach Zahlen Suchen 

```
echo "12345 namen" >> /root/namen 
grep  "[[:digit:]]\{5\}" /root/namen
```


## Cheatsheets 

  * https://cheatography.com/tme520/cheat-sheets/grep-english/



## Ref:

  * https://www.cyberciti.biz/faq/grep-regular-expressions/
