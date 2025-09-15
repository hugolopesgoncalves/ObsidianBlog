![[Pasted image 20250911120141.png]]
Osi model is used as a framework dictating how the devices send, receives and interpret data
Open Systems Interconnection 
when processes took place in the way of  how data travels, we call it encapsulation

Layer 1: physical

La couche physique, c’est comme la couche la plus basse et la plus matérielle dans la façon dont les ordinateurs parlent entre eux. Elle s’occupe des choses concrètes : les câbles, les fils, les ondes radio, les prises, et la manière dont les bits (des 0 et des 1) sont envoyés d’un appareil à un autre.

Imagine que tu veux envoyer un message en morse à ton ami avec une lampe de poche : la couche physique, c’est la lampe elle-même et la lumière qui va vers ton ami. Elle ne comprend pas le message, elle s'occupe juste de faire passer les signaux lumineux.

Cette couche ne comprend pas ce que les données veulent dire, elle s’occupe juste de transmettre les signaux, bits par bits, d’un point à un autre, pour que les couches au-dessus puissent les décoder et comprendre ce que c’est.

Layer 2 data link

La couche liaison de données est la deuxième couche du modèle OSI, juste au-dessus de la couche physique (qui s’occupe de transmettre les bits). Elle a plusieurs rôles importants.

D'abord, elle prend les données venant de la couche réseau (qui contient par exemple l'adresse IP du destinataire) et les organise en petits paquets qu'on appelle des trames. Ces trames contiennent aussi des informations importantes comme l'adresse physique, appelée adresse MAC (Media Access Control), qui est une adresse unique donnée à chaque carte réseau (NIC) de chaque appareil.

Cette adresse MAC est gravée dans la carte réseau par le fabricant et elle sert à identifier précisément qui doit recevoir les données sur le réseau local. En fait, quand on envoie des informations, c’est cette adresse physique que le réseau utilise pour savoir exactement où envoyer les données, pas l'adresse IP qui est plus logique et utilisée pour trouver des réseaux distants.

La couche liaison de données s'occupe aussi de préparer les données sous un format adapté à la transmission, de vérifier que les données n’ont pas d’erreurs, et de réguler qui peut envoyer des données et quand, pour éviter que plusieurs appareils parlent en même temps et que ça crée des collisions.

Pour simplifier, imagine que tu envoies une lettre : la couche réseau écrit l’adresse postale de la ville (adresse IP), mais la couche liaison de données écrit l’adresse précise de la maison (adresse MAC) et prépare l’enveloppe (trame) pour que la lettre arrive bien au bon destinataire. Elle vérifie aussi que la lettre n’est pas abîmée pendant le transport.

Layer 3 : network 

La couche réseau est la troisième couche du modèle OSI. C’est là que se passe la magie du routage et de la gestion des données pour voyager entre différents réseaux.

Son premier rôle est de décider du meilleur chemin pour envoyer les données d’un ordinateur à un autre, même si ces ordinateurs sont très éloignés et connectés à travers plusieurs réseaux. Ce processus s’appelle le routage.

Pour choisir ce chemin, la couche réseau regarde plusieurs critères :

- Quel est le chemin le plus court ? (c’est-à-dire par où les données doivent passer en évitant trop de points relais).
    
- Quel chemin est le plus fiable, où il y a peu de pertes de données ?
    
- Quel chemin est le plus rapide, par exemple via des câbles en fibre optique plutôt que du cuivre.
    

La couche réseau utilise des adresses logiques appelées adresses IP (exemple : 192.168.1.100) pour savoir où envoyer les données. Les appareils appelés routeurs, qui fonctionnent à cette couche (aussi appelés « couche 3 »), prennent en charge cette fonction de livraison.

Une autre chose importante : la couche réseau reconstitue les données provenant de la couche transport, qui les a découpées en petits morceaux, pour ensuite les diviser en paquets qu’elle va envoyer un par un.

En résumé, la couche réseau agit comme un service postal intelligent : elle met une adresse complète sur chaque paquet, choisit le meilleur chemin pour l’envoyer, et fait en sorte que les paquets arrivent bien au bon endroit sur Internet ou dans un réseau plus grand.

Layer 4: transport


