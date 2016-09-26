# m08_serveis_xarxa
## Escola Del Treball

#1
 ip addr  ip addr add 172.16.0.18/16 dev enp5s0

#2
 [root@i18 ~]# arp 172.16.0.16
Address                  HWtype  HWaddress           Flags Mask            Iface
172.16.0.16              ether   40:8d:5c:e3:43:59   C                     enp5s0

#3
ip link set name proba enp5s0

#4

	91.39 inbound
	91.45 outbound


#5
ifconfig hola mtu 9000

	91.33 inbound
	91.44 outbound
#Es la mateixa per que el switch limita la velocitat a 100 Mbpps

#6
 
#nmcli connection add type ethernet ifname hola ip4 172.16.0.18/16
#nmcli connection up ethernet-hola

#7 
/etc/resolv.conf
	Pedro Romero Aguado.
