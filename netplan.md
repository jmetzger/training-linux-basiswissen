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
network:
    version: 2
    renderer: networkd
    ethernets:
        enp0s3:
            addresses:
                - 10.10.10.2/24
            gateway4: 10.10.10.1
            nameservers:
                search: [mydomain, otherdomain]
                addresses: [10.10.10.1, 1.1.1.1]

```


## Referenz 

  * https://netplan.io/examples/

