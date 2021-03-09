# Kernel Modules 


## Walkthrough
```
# show kernel modules 
lsmod 
# kernel - module entladen 
modprobe -r psmouse 
lsmod | grep psmouse # now not present 
# damit wieder laden 
modprobe psmouse
lsmod | grep psmouse # now present
```

## Wo leben die Kernel - Module 

```
## kernel version is used, find out kernel version with 
uname -a 

cd /lib/modules/5.4.0-66-generic

# e.g. psmouse
find /lib/modules -name psmouse* 
/lib/modules/5.4.0-66-generic/kernel/drivers/input/mouse/psmouse.ko
```
