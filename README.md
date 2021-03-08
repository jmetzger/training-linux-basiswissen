# Linux Basiswissen 

## Agenda 

  1. [Verzeichnisaufbau](verzeichnisaufbau.md) 
  1. [Basisbefehle](basisbefehle.md)
     1. [In den Root-Benutzer wechseln](sudo.md)  
  1. [Literatur](literatur.md) 

## Verzeichnisse in Listenansicht mit versteckten Dateien anzeigen

```
ls -la 
```

## Ins Heimatverzeichnis und Wurzelverzeichnis (C: unter Windows) wechseln 

```
# Ins Heimatverzeichnis wechseln 
# cd ohne alles 
cd 

# Ins Wurzelverzeichnis 
cd / 
```

## Wie in ein Verzeichnis wechseln (relativ und absolut) 

```
# relativ - nur in ein Unterverzeichnis meines bestehenden Verzeichnisses
cd etc 

# absolut - welchselt dort rein, egal wo ich bin 
cd /etc 
```

## Wo bin ich ?

```
# 1. Ich erkenne es am prompt (Beginn  der Zeile ) 

# pwd - Print working directory 
pwd 
