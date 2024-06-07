# Jarkom-Modul-4-IT22-2024
|Nama  | NRP |
|--|--|
| Jacinta Syilloam | 5027221036 |

- VLSM: GNS3
- CIDR: CPT

# VLSM Topology @ GNS3
![image](https://github.com/JacintaSyilloam/Jarkom-Modul-4-IT22-2024/assets/121095246/053ea58c-fc77-49af-9363-64b7ea61677f)


## VLSM Tree
<img width="2393" alt="vlsm tree" src="https://github.com/JacintaSyilloam/Jarkom-Modul-4-IT22-2024/assets/121095246/33b2fbad-9d6c-4519-87e0-616a38041ee2">


## Subnet Information

| Subnet | Network ID    | Netmask         | Broadcast       | Range IP                     |
|--------|---------------|-----------------|-----------------|------------------------------|
| A1     | 192.244.0.0   | 255.255.248.0   | 192.244.7.255   | 192.244.0.1 - 192.244.7.254  |
| A2     | 192.244.8.0   | 255.255.248.0   | 192.244.15.255  | 192.244.8.1 - 192.244.15.254 |
| A3     | 192.244.16.0  | 255.255.254.0   | 192.244.17.255  | 192.244.16.1 - 192.244.17.254|
| A4     | 192.244.18.0  | 255.255.255.0   | 192.244.18.255  | 192.244.18.1 - 192.244.18.254|
| A5     | 192.244.19.0  | 255.255.255.0   | 192.244.19.255  | 192.244.19.1 - 192.244.19.254|
| A6     | 192.244.20.0  | 255.255.255.128 | 192.244.20.127  | 192.244.20.1 - 192.244.20.126|
| A7     | 192.244.20.128| 255.255.255.128 | 192.244.20.255  | 192.244.20.129 - 192.244.20.254|
| A8     | 192.244.21.0  | 255.255.255.192 | 192.244.21.63   | 192.244.21.1 - 192.244.21.62 |
| A9     | 192.244.21.64 | 255.255.255.224 | 192.244.21.95   | 192.244.21.65 - 192.244.21.94 |
| A10    | 192.244.21.96 | 255.255.255.224 | 192.244.21.127  | 192.244.21.97 - 192.244.21.126|
| A11    | 192.244.21.128| 255.255.255.224 | 192.244.21.159  | 192.244.21.129 - 192.244.21.158|
| A12    | 192.244.21.160| 255.255.255.248 | 192.244.21.167  | 192.244.21.161 - 192.244.21.166|
| A13    | 192.244.21.168| 255.255.255.248 | 192.244.21.175  | 192.244.21.169 - 192.244.21.174|
| A14    | 192.244.21.176| 255.255.255.252 | 192.244.21.179  | 192.244.21.177 - 192.244.21.178|
| A15    | 192.244.21.180| 255.255.255.252 | 192.244.21.183  | 192.244.21.181 - 192.244.21.182|
| A16    | 192.244.21.184| 255.255.255.252 | 192.244.21.187  | 192.244.21.185 - 192.244.21.186|
| A17    | 192.244.21.188| 255.255.255.252 | 192.244.21.191  | 192.244.21.189 - 192.244.21.190|
| A18    | 192.244.21.192| 255.255.255.252 | 192.244.21.195  | 192.244.21.193 - 192.244.21.194|
| A19    | 192.244.21.196| 255.255.255.252 | 192.244.21.199  | 192.244.21.197 - 192.244.21.198|
| A20    | 192.244.21.200| 255.255.255.252 | 192.244.21.203  | 192.244.21.201 - 192.244.21.202|
| A21    | 192.244.21.204| 255.255.255.252 | 192.244.21.207  | 192.244.21.205 - 192.244.21.206|


## Network && Routing Configuration @ GNS3
```
###### JAWA
auto eth0
iface eth0 inet dhcp

# A15
auto eth1
    iface eth1 inet static
    address 192.244.21.181
    netmask 255.255.255.252
    gateway 192.244.21.182

# A17
auto eth2
    iface eth2 inet static
    address 192.244.21.189
    netmask 255.255.255.252
    gateway 192.244.21.190

# A16
auto eth3
    iface eth3 inet static
    address 192.244.21.185
    netmask 255.255.255.252
    gateway 192.244.21.186

# JAWA - Gateway SUMATERA
route add -net 192.244.21.64 netmask 255.255.255.224 gw 192.244.21.182 
route add -net 192.244.21.176 netmask 255.255.255.252 gw 192.244.21.182 
route add -net 192.244.21.200 netmask 255.255.255.252 gw 192.244.21.182 
route add -net 192.244.21.128 netmask 255.255.255.224 gw 192.244.21.182 
route add -net 192.244.20.0 netmask 255.255.255.128 gw 192.244.21.182 
route add -net 192.244.19.0 netmask 255.255.255.0 gw 192.244.21.182 

# JAWA - Gateway KALIMANTAN
route add -net 192.244.21.192 netmask 255.255.255.252 gw 192.244.21.186 
route add -net 192.244.21.196 netmask 255.255.255.252 gw 192.244.21.186 
route add -net 192.244.18.0 netmask 255.255.255.0 gw 192.244.21.186 
route add -net 192.244.21.204 netmask 255.255.255.252 gw 192.244.21.186 
route add -net 192.244.16.0 netmask 255.255.254.0 gw 192.244.21.186
route add -net 192.244.0.0 netmask 255.255.248.0 gw 192.244.21.186
route add -net 192.244.21.96 netmask 255.255.255.224 gw 192.244.21.186

# JAWA - Gateway SULAWESI
route add -net 192.244.21.160 netmask 255.255.255.248 gw 192.244.21.190
route add -net 192.244.21.168 netmask 255.255.255.248 gw 192.244.21.190
route add -net 192.244.21.0 netmask 255.255.255.192 gw 192.244.21.190
route add -net 192.244.20.128 netmask 255.255.255.128 gw 192.244.21.190
route add -net 192.244.8.0 netmask 255.255.248.0 gw 192.244.21.190



##### SUMATERA
# A15
auto eth0
    iface eth0 inet static
    address 192.244.21.182
    netmask 255.255.255.252
    gateway 192.244.21.181
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A14
auto eth1
    iface eth1 inet static
    address 192.244.21.177
    netmask 255.255.255.252
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A9
auto eth2
    iface eth2 inet static
    address 192.244.21.65
    netmask 255.255.255.224
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# SUMATERA
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.244.21.181

# SUMATERA - Gateway SUMATERA-UTARA
route add -net 192.244.21.200 netmask 255.255.255.252 gw 192.244.21.68
route add -net 192.244.20.0 netmask 255.255.255.128 gw 192.244.21.68
route add -net 192.244.21.128 netmask 255.255.255.224 gw 192.244.21.68

# SUMATERA - Gateway LAMPUNG
route add -net 192.244.19.0 netmask 255.255.255.0 gw 192.244.21.178



##### Samosir (14 host)
# A9
auto eth0
    iface eth0 inet static
    address 192.244.21.66
    netmask 255.255.255.224
    gateway 192.244.21.65
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Sibandang (11 host)
# A9
auto eth0
    iface eth0 inet static
    address 192.244.21.67
    netmask 255.255.255.224
    gateway 192.244.21.65
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### SUMATERA-UTARA
# A9
auto eth0
    iface eth0 inet static
    address 192.244.21.68
    netmask 255.255.255.224
    gateway 192.244.21.65
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A20
auto eth1
    iface eth1 inet static
    address 192.244.21.201
    netmask 255.255.255.252
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# SUMATERA-UTARA
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.244.21.65

# SUMATERA-UTARA - Gateway SUMATERA-UTARA
route add -net 192.244.20.0 netmask 255.255.255.128 gw 192.244.21.202
route add -net 192.244.21.128 netmask 255.255.255.224 gw 192.244.21.202


##### ACEH
# A20
auto eth0
    iface eth0 inet static
    address 192.244.21.202
    netmask 255.255.255.252
    gateway 192.244.21.201
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A6
auto eth1
    iface eth1 inet static
    address 192.244.20.1
    netmask 255.255.255.224
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A11
auto eth2
    iface eth2 inet static
    address 192.244.21.129
    netmask 255.255.255.224
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# ACEH
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.244.21.201


##### Berawang-Tampu (53 host)
# A6
auto eth0
    iface eth0 inet static
    address 192.244.20.2
    netmask 255.255.255.128
    gateway 192.244.20.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Enang-Enang (27 host)
# A6
auto eth0
    iface eth0 inet static
    address 192.244.20.3
    netmask 255.255.255.128
    gateway 192.244.20.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Starland (44 host)
# A6
auto eth0
    iface eth0 inet static
    address 192.244.20.4
    netmask 255.255.255.128
    gateway 192.244.20.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Sabang (6 host)
# A11
auto eth0
    iface eth0 inet static
    address 192.244.21.130
    netmask 255.255.255.224
    gateway 192.244.21.129
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Lambaro (8 host)
# A11
auto eth0
    iface eth0 inet static
    address 192.244.21.131
    netmask 255.255.255.224
    gateway 192.244.21.129
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### LAMPUNG
# A14
auto eth0
    iface eth0 inet static
    address 192.244.21.178
    netmask 255.255.255.252
    gateway 192.244.21.177
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A5
auto eth1
    iface eth1 inet static
    address 192.244.19.1
    netmask 255.255.255.0
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# LAMPUNG
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.244.21.177


##### Sebuku (186 host)
# A5
auto eth0
    iface eth0 inet static
    address 192.244.19.2
    netmask 255.255.255.0
    gateway 192.244.19.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Sebesi (Server)
# A5
auto eth0
    iface eth0 inet static
    address 192.244.19.3
    netmask 255.255.255.0
    gateway 192.244.19.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### SULAWESI
# A17
auto eth0
    iface eth0 inet static
    address 192.244.21.190
    netmask 255.255.255.252
    gateway 192.244.21.189
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A12
auto eth1
    iface eth1 inet static
    address 192.244.21.161
    netmask 255.255.255.248
    gateway 192.244.21.162
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A7
auto eth2
    iface eth2 inet static
    address 192.244.20.129
    netmask 255.255.255.128
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# SULAWESI
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.244.21.189

# SULAWESI - Gateway MAKASSAR
route add -net 192.244.21.168 netmask 255.255.255.248 gw 192.244.21.162

# SULAWESI - Gateway MALUKU-UTARA
route add -net 192.244.8.0 netmask 255.255.248.0 gw 192.244.20.132

# SULAWESI - Gateway BELAWA
route add -net 192.244.21.0 netmask 255.255.255.192 gw 192.244.21.163


##### PC-Gorontalo (32 host)
# A7
auto eth0
    iface eth0 inet static
    address 192.244.20.130
    netmask 255.255.255.128
    gateway 192.244.20.129
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### PC-Marisa (30 host)
# A7
auto eth0
    iface eth0 inet static
    address 192.244.20.131
    netmask 255.255.255.128
    gateway 192.244.20.129
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### MALUKU-UTARA
# A7
auto eth0
    iface eth0 inet static
    address 192.244.20.132
    netmask 255.255.255.128
    gateway 192.244.20.129
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A2
auto eth1
    iface eth1 inet static
    address 192.244.8.1
    netmask 255.255.248.0
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# MALUKU-UTARA
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.244.20.129


##### Tobelo (511 host)
# A2
auto eth0
    iface eth0 inet static
    address 192.244.8.2
    netmask 255.255.248.0
    gateway 192.244.8.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Morotai (Server)
# A2
auto eth0
    iface eth0 inet static
    address 192.244.8.3
    netmask 255.255.248.0
    gateway 192.244.8.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Ternate (511 host)
# A2
auto eth0
    iface eth0 inet static
    address 192.244.8.4
    netmask 255.255.248.0
    gateway 192.244.8.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### MAKASSAR
# A12
auto eth0
    iface eth0 inet static
    address 192.244.21.162
    netmask 255.255.255.248
    gateway 192.244.21.161
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A20
auto eth1
    iface eth1 inet static
    address 192.244.21.169
    netmask 255.255.255.248
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# MAKASSAR
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.244.21.161 


##### Galesong (Server)
# A13
auto eth0
    iface eth0 inet static
    address 192.244.21.170
    netmask 255.255.255.248
    gateway 192.244.21.169
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Topejawa-Takalar (Server)
# A13
auto eth0
    iface eth0 inet static
    address 192.244.21.171
    netmask 255.255.255.248
    gateway 192.244.21.169
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### BELAWA
# A12
auto eth0
    iface eth0 inet static
    address 192.244.21.163
    netmask 255.255.255.248
    gateway 192.244.21.161
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A8
auto eth1
    iface eth1 inet static
    address 192.244.21.1
    netmask 255.255.255.192
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# BELAWA
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.244.21.161


##### Madini (30 host)
# A8
auto eth0
    iface eth0 inet static
    address 192.244.21.2
    netmask 255.255.255.192
    gateway 192.244.21.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Baru (30 host)
# A8
auto eth0
    iface eth0 inet static
    address 192.244.21.3
    netmask 255.255.255.192
    gateway 192.244.21.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### KALIMANTAN
# A16 
auto eth0
    iface eth0 inet static
    address 192.244.21.186
    netmask 255.255.255.252
    gateway 192.244.21.185
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A18
auto eth1
    iface eth1 inet static
    address 192.244.21.193
    netmask 255.255.255.252
    gateway 192.244.21.194
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# KALIMANTAN
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.244.21.185

# KALIMANTAN - Gateway KALIMANTAN-UTARA
route add -net 192.244.18.0 netmask 255.255.255.0 gw 192.244.21.194
route add -net 192.244.21.196 netmask 255.255.255.252 gw 192.244.21.194
route add -net 192.244.16.0 netmask 255.255.254.0 gw 192.244.21.194
route add -net 192.244.21.204 netmask 255.255.255.252 gw 192.244.21.194
route add -net 192.244.21.96 netmask 255.255.255.224 gw 192.244.21.194
route add -net 192.244.0.0 netmask 255.255.248.0 gw 192.244.21.194 


##### KALIMANTAN-UTARA
# A18
auto eth0
    iface eth0 inet static
    address 192.244.21.194
    netmask 255.255.255.252
    gateway 192.244.21.193
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A4
auto eth1
    iface eth1 inet static
    address 192.244.18.1
    netmask 255.255.255.0
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A19
auto eth2
    iface eth2 inet static
    address 192.244.21.197
    netmask 255.255.255.252
    gateway 192.244.21.198
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# KALIMANTAN-UTARA 
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.244.21.193

# KALIMANTAN-UTARA - Gateway KALIMANTAN-TIMUR
route add -net 192.244.16.0 netmask 255.255.254.0 gw 192.244.21.198 
route add -net 192.244.21.204 netmask 255.255.255.252 gw 192.244.21.198 
route add -net 192.244.21.96 netmask 255.255.255.224 gw 192.244.21.198 
route add -net 192.244.0.0 netmask 255.255.248.0 gw 192.244.21.198 


##### Selimau (200 host)
# A4
auto eth0
    iface eth0 inet static
    address 192.244.18.2
    netmask 255.255.255.0
    gateway 192.244.18.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### KALIMANTAN-TIMUR
# A19
auto eth0
    iface eth0 inet static
    address 192.244.21.198
    netmask 255.255.255.252
    gateway 192.244.21.197
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A3
auto eth1
    iface eth1 inet static
    address 192.244.16.1
    netmask 255.255.254.0
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A21
auto eth2
    iface eth2 inet static
    address 192.244.21.205
    netmask 255.255.255.252
    gateway 192.244.21.206
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# KALIMANTAN-TIMUR
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.244.21.197 

# KALIMANTAN-TIMUR - Gateway KALIMANTAN-SELATAN
route add -net 192.244.21.96 netmask 255.255.255.224 gw 192.244.21.206 
route add -net 192.244.0.0 netmask 255.255.248.0 gw 192.244.21.206 


##### Bangkirai (Server)
# A3
auto eth0
    iface eth0 inet static
    address 192.244.16.3
    netmask 255.255.254.0
    gateway 192.244.16.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Lamaru (Server)
# A3
auto eth0
    iface eth0 inet static
    address 192.244.16.2
    netmask 255.255.254.0
    gateway 192.244.16.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### KALIMANTAN-SELATAN
# A21 
auto eth0
    iface eth0 inet static
    address 192.244.21.206
    netmask 255.255.255.252
    gateway 192.244.21.205
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A10
auto eth1
    iface eth1 inet static
    address 192.244.21.97
    netmask 255.255.255.224
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# A1
auto eth2
    iface eth2 inet static
    address 192.244.0.1
    netmask 255.255.248.0
    up echo nameserver 192.168.122.1 > /etc/resolv.conf

# KALIMANTAN-SELATAN
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.244.21.205       


##### Angsana (15 host)
# A10
auto eth0
    iface eth0 inet static
    address 192.244.21.98
    netmask 255.255.255.224
    gateway 192.244.21.97
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Bajuin (511 host)
# A1
auto eth0
    iface eth0 inet static
    address 192.244.0.4
    netmask 255.255.248.0
    gateway 192.244.0.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Takisung (513 host)
# A1
auto eth0
    iface eth0 inet static
    address 192.244.0.3
    netmask 255.255.248.0
    gateway 192.244.0.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf


##### Batakan (1020 host)
# A1
auto eth0
    iface eth0 inet static
    address 192.244.0.2
    netmask 255.255.248.0
    gateway 192.244.0.1
    up echo nameserver 192.168.122.1 > /etc/resolv.conf
```


## Testing GNS3
Ping from each node to all node: [https://youtu.be/m1WV8f6igF8](https://youtu.be/m1WV8f6igF8)


### Preview
![image](https://github.com/JacintaSyilloam/Jarkom-Modul-4-IT22-2024/assets/121095246/e8bdd4b7-f29a-4045-976e-035b2264f477)


# CIDR Topology @ CPT
