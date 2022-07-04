# Aliase 

## Alias anzeigen

```
# keine wirkliche Befehle, sondern nur andere Schreibweise/Abkürzungen
# kann u.U. so auf anderen Distris nicht vorhanden sein
alias 
```

## Alias anlegen 

```
# in der Session 
alias hallo='ls -la'

# persistent bei jedem aufruf einer bash 
# unter ubuntu 20.04.
# bash_aliases wird in ~/.bashrc geladen 
echo "alias hallo2='ls -la'" > ~/.bash_aliases 

# zum Testen 
# 1. Entweder 
# Neue bash starten 
bash 
# Sourcen zum einmaligen Testen
source ~/.bash_aliases 


```
