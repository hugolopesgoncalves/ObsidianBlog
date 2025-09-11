![[Pasted image 20250911120141.png]]
Osi model is used as a framework dictating how the devices send, receives and interpret data
Open Systems Interconnection 
when processes took place in the way of  how data travels, we call it encapsulation

Layer 1: physical

La couche physique, c’est comme la couche la plus basse et la plus matérielle dans la façon dont les ordinateurs parlent entre eux. Elle s’occupe des choses concrètes : les câbles, les fils, les ondes radio, les prises, et la manière dont les bits (des 0 et des 1) sont envoyés d’un appareil à un autre.

Imagine que tu veux envoyer un message en morse à ton ami avec une lampe de poche : la couche physique, c’est la lampe elle-même et la lumière qui va vers ton ami. Elle ne comprend pas le message, elle s'occupe juste de faire passer les signaux lumineux.

Cette couche ne comprend pas ce que les données veulent dire, elle s’occupe juste de transmettre les signaux, bits par bits, d’un point à un autre, pour que les couches au-dessus puissent les décoder et comprendre ce que c’est.

Layer 2 data link

La couche liaison de données, c’est la couche juste au-dessus de la couche physique. Si la couche physique s’occupe d’envoyer les bits (0 et 1) via le câble ou le signal, la couche liaison de données elle, s’assure que ces bits sont bien organisés et envoyés correctement d’un appareil à un autre sur le même réseau.

Imagine que tu écris un message sur des feuilles séparées (les bits envoyés par la couche physique), la couche liaison de données va rassembler ces feuilles en un paquet bien ordonné (qu’on appelle une trame), vérifier qu’il n’y a pas d’erreur, et gérer quand chaque appareil peut envoyer ses données pour éviter des collisions.

Elle aide aussi à reconnaître les appareils réseau entre eux, par exemple grâce à des adresses physiques (comme les adresses MAC), pour que les données arrivent bien à la bonne machine.