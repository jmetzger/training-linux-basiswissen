# Netzwerkkonfiguration mit Netplan 

## Desktop 

```
# /etc/netplan/01-network-manager-all.yaml
# On Desktop-Systems everything is handled by the Network-Manager 
# Let NetworkManager manage all devices on this system
network:
  version: 2
  renderer: NetworkManager
```

## Umschalten auf anderen Renderer 

```
# ...yaml
network:
    version: 2
    renderer: networkd
    ethernets:
        enp0s3:
            dhcp4: true

# check  changes 
netplan try 
# apply changes
netplan apply 

```

## Statische Adresse konfigurieren 

```
# routing rausfinden
ip route 
```

```
# Verwendete Nameserver rausfinden


```
enp0s8:
  addresses:
  - 192.168.56.101/24
  routes:
    - to: default
      via: 10.10.10.1
  nameservers:
    search: [training.local]
    addresses: [8.8.8.8]
```

```
netplan apply ---debug 
# or
netplan apply
# or 
netplan try 
```

## Interface händisch (nicht persistent) stoppen 

```
ip link set dev enp0s8 down
```


## Alternative: ifupdown - package als Alternative 

  * Empfehlung: Wir bleiben dabei, was das System mir anbieten (also netplan) 
  * ifupdown bietet die klassischen /etc/network/interfaces zur Konfiguration 


## Referenz 

  * https://netplan.io/examples/

