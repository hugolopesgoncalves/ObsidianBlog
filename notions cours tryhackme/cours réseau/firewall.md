use to determine what traffic is allowed or not to enter/exit the network
thats a security boundarie

it permit data to traval with those categories.what protocol is the traffic using


.is the source device trustable
.is the destination source trustable
.what port is the traffic for
.what protocol is the traffic unsing (you can for exemple ban a certain packet UDP or TCp to be ban for exemple)
![[Pasted image 20250917045538.png]]
## Action DROP

- Le firewall élimine les paquets non désirés sans envoyer de message à la source, ce qui rend le blocage invisible pour l’expéditeur, pouvant entraîner des "timeouts" de connexion côté client.[cyber+2](https://cyber.gouv.fr/sites/default/files/IMG/pdf/NP_Politique_pare_feu_NoteTech.pdf)
    
- Cette action sert à rendre l'analyse par des attaquants plus difficile, car elle ne révèle pas que le port ou l’adresse cible est bien protégée.[knowledgebase.paloaltonetworks+1](https://knowledgebase.paloaltonetworks.com/KCSArticleDetail?id=kA10g000000ClltCAC&lang=fr)
    
- DROP est donc utilisé pour renforcer la discrétion et limiter l’exposition aux attaques automatisées ou au scan de ports.[cyber+1](https://cyber.gouv.fr/sites/default/files/IMG/pdf/NP_Politique_pare_feu_NoteTech.pdf)
    

## Action PASS

- L’action PASS permet explicitement à un paquet de passer au travers du firewall, ce qui correspond à une autorisation du trafic concerné.[cisco.goffinet+1](https://cisco.goffinet.org/ccna/filtrage/lab-pare-feu-cisco-ios-zbf-zone-based-firewall/)
    
- Ce n'est pas un suivi d'état (stateful), donc pour certains protocoles, il faut aussi autoriser la réponse si nécessaire.[cisco.goffinet](https://cisco.goffinet.org/ccna/filtrage/lab-pare-feu-cisco-ios-zbf-zone-based-firewall/)
    
- Cette action est typiquement utilisée pour les flux de confiance ou les exceptions dans une politique restrictive.