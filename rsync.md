# Rsync / Nur geänderte Dateien auf anderen Server schicken

```
rsync --links -u -v -e ssh -r /var kurs@192.168.56.102:/home/kurs
```
