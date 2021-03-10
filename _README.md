# Linux Basiswissen 


## Agenda
  1. Verzeichnisse und Dateitypen 
     * [Verzeichnisaufbau](verzeichnisaufbau.md)
     * [Dateitypen](dateitypen.md) 
  1. Basisbefehle
     1. [In den Root-Benutzer wechseln](sudo.md)  
     1. [Wo bin ich ?](pwd.md)
     1. [Praktische Ausgabe von langen Seite - less](less.md) 
     1. [Datei anlegen - touch](touch.md)
     1. [Autovervollständen * and tab](autocomplete.md) 
     1. [Welche Programm wird verwendet](which.md)
  1. Dateien und Verzeichnisse
     1. [Inhalt in Datei schreiben und anhängen](file-write-append.md)
     1. [Verzeichnisse und Dateien löschen](file-dir-delete.md)
     1. [Kopieren/Verschieben/umbenennen](file-rename-copy-move.md) 
  1. Prozesse 
     1. [Prozesse anzeigen - ps/pstree -p](prozesse.md)
  1. Benutzer, Gruppen und Rechte 
     1. [Rechte](rechte.md) 
     1. [Dateien für Benutzer und Gruppen](files-users-groups.md) 
     1. [Benutzer anlegen](create-users.md) 
     1. [sudo Benutzer erstellen](mod-user-sudo.md) 
  1. Dateimanipulation/Unix Tools
     1. [cat/head/tail-Beginn/Ende einer Datei anzeigen](cat-head.md)
     1. [zcat - Inhalte einer mit gzip komprimierten Datei anzeigen](zcat.md)
     1. [wc - zeilen zählen](wc.md)
     1. [bestimmte Zeilen aus Datei anzeigen - grep](grep.md)
  1. Logs/Loganalyse
     1. [Logfile beobachten](tailf.md)
  1. Variablen
     1. [Setzen und verwenden von Variablen](variables.md) 
  1. Dienste/Runlevel(Targets verwalten) 
     1. [Die wichtigsten systemctl/service](systemctl-service.md)
  1. Partitionierung und Filesystem
     1. [parted and mkfs.ext4](parted-mkfs.md)
  1. Boot-Prozess und Kernel 
     1. [Grub konfigurieren](grub.md)
     1. [Kernel-Version anzeigen](kernel-version.md) 
     1. [Kernel-Module laden/entladen/zeigen](kernel-modules.md) 
  1. Hilfe 
     1. [Hilfe zu Befehlen](help.md)
  1. Literatur 
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


<div class="page-break"></div>

## Verzeichnisse und Dateitypen 

### Verzeichnisaufbau


### /etc 

  * Verzeichnis für Konfigurationsdatein 

### /dev 

  * Devices (Alle Gerätedateien - Ein- und Ausgabegeräte, wie bspw. Festplatten, Mouse) 

### /mnt 

  * früher viel verwendet: 
  * für händisches Einhängen gedacht (per Hand mounten) 
 
### /media 

  * das neue / moderne (wird heutzutage meistens verwendet) 
  * Verzeichnis für automatisch eingehängte Devices (z.B. usb-stick)

### /opt 

  * Große Softwarepaket (z.B. LibreOffice, OpenOffice, Dritt-Anbieter) 

### /boot 
 
  * Files for booting (e.g. kernel, grub.cfg, initital ramdisk)

### /proc 

  + Schnittstelle zwischen Kernel und User-Space (für Programme, Benutzer)
  + Kommunikation erfolgt über Dateien 

### /root 
  
  * Heimatverzeichnis des root-Benutzers 

### /run 

  * Dateien mit Prozess-ID für laufenden Services
  * um diese gut beenden zu können 

### /tmp 

  * Temporäre Dateien 
  * Löschen von Dateien kann unter /etc/tmpfiles.d verwaltet werden (erfolgt von systemd auf Tagesbasis) 

### /sys 

  * wie proc 
  * Schnittstelle zwischen Kernel und User-space 

### /var (=variable daten) 

  * Hier liegen Daten, die sich häufig ändern
  * Log-Dateien, Datenbanken, Spool-Dateien, Cache-Dateien 

### /lib 

  * Bibliotheken (.so, .ko) wie unter Windows *dll's 

### /sbin

  * Programme zur Systemadministration 

### /bin 

  * Normale Programme für alle (executables) 

<div class="page-break"></div>

### Dateitypen


### Wo ? 

  * Erste Spalte bei ls -la 

### Welche ? 

```
- file 
d directory 
l symbolischer Link 
c Character-Device (Eingabegerät: Zeichenorientiert z.B. Tastatur)  
b Block-Device (Ausgabegerät): Blockorientiert, z.B. Festplatte) 
```

<div class="page-break"></div>

## Basisbefehle

## Dateien und Verzeichnisse

## Prozesse 

## Benutzer, Gruppen und Rechte 

## Dateimanipulation/Unix Tools

## Logs/Loganalyse

## Variablen

## Dienste/Runlevel(Targets verwalten) 

## Partitionierung und Filesystem

## Boot-Prozess und Kernel 

## Hilfe 

## Literatur 
