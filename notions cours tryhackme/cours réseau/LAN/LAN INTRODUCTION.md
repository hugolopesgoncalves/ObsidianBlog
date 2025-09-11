Star Topology : All devices connected to a main one (switch/hub)
Expensive HUB+lots of wires 
if hub broke == all brocken
![[Pasted image 20250911063738 1.png]]

Bus topology : All devices connected upon a single wire connection (backbone cable) slow because if there is a lot of information the traffic is gonna be bottle necked
Less expensive no hub
if a device broke == still fonctionnable

![[Pasted image 20250911063726.png]]
Ring topoloogy/token topology: computers are connected directly to each others to from a loop
if a wire is cut == all brocken
![[Pasted image 20250911064258.png]]
a switch is use to connect devices
a router is use to connect networks root = connecter

subnets ip adress

![[Pasted image 20250911112502.png]]
interessant dans ce tableau : les explications et exemple comme adresse generique de reseau xxx.xxx.xxx.0 pour adresse de réseau et xxx.xxx.xxx.254 pour adresse de routeur(gateway)

une adresse de gateway/routeur est l'adresse par laquelle les infos transitent en dehors du réseau (sur un autre réseau)

the adress used to identify the start of a network : the network adress

the adress to identify a device within a network : the host adress

the name to identify the device responsible to send datas to another network : gateway

ARP: ARP allows a device to associate its MAC address with an IP address on the network. Each device on a network will keep a log of the MAC addresses associated with other devices in  a ledger

comment ça marche?
Chaque appareil sur le reseau envoie une demande à tous les autres device quel est la mac adress associé à chaque ip adress du reseau, le device concerné repond et l'apareil stoque la réponse dans un ledger (livre de compte)

1. **ARP Request**
2. **ARP Reply**
![[Pasted image 20250911114556.png]]
DHCP server
IP addresses can be assigned either manually, by entering them physically into a device, or automatically and most commonly by using a **DHCP** (**D**ynamic **H**ost **C**onfiguration **P**rotocol) server. When a device connects to a network, if it has not already been manually assigned an IP address, it sends out a request (DHCP Discover) to see if any DHCP servers are on the network. The DHCP server then replies back with an IP address the device could use (DHCP Offer). The device then sends a reply confirming it wants the offered IP Address (DHCP Request), and then lastly, the DHCP server sends a reply acknowledging this has been completed, and the device can start using the IP Address (DHCP ACK).

![[Pasted image 20250911115615.png]]