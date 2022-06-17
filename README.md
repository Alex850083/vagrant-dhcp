# testdhcp

Протестировано в Debian 10 "buster"
Дополнительно нужно создать bridge -  vmbr76
  
```
cat /etc/network/interfaces
...
auto vmbr76
iface vmbr76 inet static
        address 192.168.76.254/24
        bridge-ports none
        bridge-stp off
        bridge-fd 0

```
