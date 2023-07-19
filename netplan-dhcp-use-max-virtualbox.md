# Change settings netplan for getting a new ip from DHCP by mac

## Walkthrough 

```
network:
  ethernets:
    eth0:
      dhcp4: true
      dhcp-identifier: mac
  version: 2
```


## Ref:

  * https://nickvsnetworking.com/ubuntu-cloned-vms-getting-duplicate-ips-and-the-mas-the-same/
