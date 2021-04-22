# Spanning-Tree Protocol
Spanning Tree Protocol é um protocolo para equipamentos de rede que permite resolver problemas de loop em redes comutadas cuja topologia introduza anéis nas ligações, auxiliando na melhor performance da rede.




## PROJETO 7
1. Configuramos os endereços nos PCs
2. Configuramos todas as 5 VLANs em todos os Switches
3. Configuramos as portas dos Switches que ligam os PCs em suas respectivas VLAN
4. Configuramos Trunk em todas as interligações dos Switches
5. Definimos como Switch Root o SW-CORE (3560 L3) para todas as 5 VLANs

Comando utilizado no SW-CORE para definir o root:
* SW-CORE(config)#spanning-tree vlan 10 priority 4096
* SW-CORE(config)#spanning-tree vlan 20 priority 4096
* SW-CORE(config)#spanning-tree vlan 30 priority 4096
* SW-CORE(config)#spanning-tree vlan 40 priority 4096
* SW-CORE(config)#spanning-tree vlan 50 priority 4096

## TOPOLOGIA
![Aula-07](https://user-images.githubusercontent.com/71797851/115643322-ee603580-a2f2-11eb-9ae4-ddd8fc3b3b60.png)
