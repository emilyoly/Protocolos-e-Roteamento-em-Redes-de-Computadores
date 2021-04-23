# PROJETO 4 - VLAN - Trunk: Protocolo dot1q

Uma porta de um Switch configurada e ligada com outra porta na modalidade TRUNK, permite que várias VLANs trafeguem por ela, diferentemente se tivemos uma porta definida apenas com uma determinada
VLAN.

![projeto4](https://user-images.githubusercontent.com/71797851/115802684-bcfc6e00-a3b5-11eb-817a-7a26c069ba7f.png)

O projeto 4 contempla uma rede com roteamento tradicional (1 placa de rede no Router, para cada VLAN) mais a ligação em TRUNKING entre os dois Switches.

## Requisitos Iniciais: Situação Virtual

ADMINISTRAÇÃO
* Switch 2960-24T 
* 3 PCS

ENGENHARIA
* Switch 2960-24T
* 3 PCS

ROUTER CORE: 2901

## TOPOLOGIA
![topologia-projeto4](https://user-images.githubusercontent.com/71797851/115802945-35632f00-a3b6-11eb-95e2-2f8cb5286e13.png)


## SCRIPTS

Router:
```sh
en
conf t
hostname RT-CORE
interface Gig0/0
ip address 192.168.0.1 255.255.255.0
no shutdown
exit
interface Gig0/1
ip address 172.16.0.1 255.255.255.0
no shutdown
end
wr
```

Swith Administração:
```sh
en
conf t
hostname SW-ADM
vlan 10
name ADM
vlan 20
name ENG
exit
interface range Fa0/1-Fa0/24
swithport access vlan 10
exit
interface fa0/4
switchport access vlan 20
exit
interface gig0/1
switchport mode trunk
end
wr
```

Swith Engenharia:
```sh
en
conf t
hostname SW-ENG
vlan 10
name ADM
vlan 20
name ENG
exit
interface range Fa0/1-Fa0/24
swithport access vlan 20
exit
interface fa0/4
switchport access vlan 10
exit
interface gig0/1
switchport mode trunk
end
wr
```
