# Priorität und Niceness 

## nice aus dem userspace möglich

```
# userspace - ich führe als Benutzer ein Programm 
# nice - Festlegen ein programm zum Kernel ist 

# Priorität in top - pr 
# je niedriger die Zahl für den Prozess in top ist, desto 
# höher die Priorität 
# höchste Prioriät -100 
-100 bis 39 

# -100 = rt 
# Statt -100 steht rt dort in top in der Spalte PR 

# -59 höhe Priorität als 0 als 20 etc. 

# Aus nice - Anfragen. von -20 -> +19 machen der Kernel
# in der Regel 
n + 20 z.B. Niceness= -20. = -20 + 20 = 0
# D.h. höchte Prioriät über nice im Kernel ist 0 
# die niedrigste Priorität 39 

```

## Prozesse in Realtime ausführen wie geht ? 

```
chrt # change realtime 

```

## Ref:

  * https://medium.com/@joseagustin.barra/understanding-priority-levels-in-linux-cd8c82eb4dd
