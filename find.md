# Find 

## Suchen nach allen Vorkommen im Verzeichnis /etc mit 'ssh' im Namen  

```
# Bitte immer einfach Hochkommas verwenden.
find /etc -iname 'ssh*'
# Wäre das gleiche wie. 
find /etc -iname 'ssh*' -print 
```

## Suchen nach allen Vorkommen von mariadb 

```
# iname - case insensitive 
find / -iname '*mariadb*' 
```

## Simple find command 

```
# find directories with specific name 
find / -name tmpfiles.d -type d 
find /etc -name 'ssh*' -type f
```
