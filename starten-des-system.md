# Systemstart 

## Reihenfolge (Phase 1) 

```
1. BIOS-Selbsttest 
2. MBR (512 Bytes auf der Festplatte) -> Bootloader Teil 1.
3. Bootmanager (Grub) wird gestartet 
4. Im Boot-Manager -> Auswahl welcher Eintrag soll verwendet werden 
5. Mutter aller Prozesse -> init -> systemd 
```

### Reihenfolge (Phase 2) - systemd hat die Kontrolle 

```
# in welchen Endmodus -> Target soll ich mich hocharbeiten 
graphical.target 

graphical.target (isolateTarget) 
   multi-user.target (isolatedTarget)
      basic.target 
```
