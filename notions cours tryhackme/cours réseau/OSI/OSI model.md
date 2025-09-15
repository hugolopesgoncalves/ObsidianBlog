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


La couche transport (couche 4 du modèle OSI) est essentielle car elle gère la transmission fiable ou non des données entre deux appareils. Elle s’appuie principalement sur deux protocoles : TCP et UDP. Voici une explication en français, adaptée à partir de ton texte :

---

## La couche transport (TCP/UDP)

La couche transport du modèle OSI a pour rôle d’assurer le déplacement des données entre deux hôtes connectés à un réseau. Elle segmente les données reçues de la couche session (couche 5), les convertit en petits paquets, puis s’assure que ces paquets atteignent leur destination correcte. Deux protocoles principaux opèrent ici : TCP et UDP.

---

## Transmission Control Protocol (TCP)

Le protocole TCP est conçu pour la **fiabilité** et la **garantie de livraison**.

- Il établit une connexion stable entre les deux dispositifs pendant toute la durée de la transmission.
    
- Il incorpore des mécanismes de **contrôle d’erreurs**, garantissant que les paquets de données sont reçus et réassemblés dans le bon ordre.
    

## Avantages de TCP

- Assure l’exactitude des données.
    
- Peut synchroniser deux appareils afin d’éviter une surcharge de données.
    
- Idéal pour les applications nécessitant une intégrité complète (navigateur web, e-mails, partage de fichiers).
    

## Inconvénients de TCP

- Nécessite une connexion fiable (si un paquet manque, la transmission est bloquée).
    
- Connexion lente ou instable = goulot d’étranglement.
    
- Plus lent qu’UDP car il effectue de nombreux contrôles.
    

---

## User Datagram Protocol (UDP)

Le protocole UDP est beaucoup plus simple et rapide que TCP, mais ne propose pas les mêmes garanties.

- Il _ne vérifie pas_ si les paquets atteignent leur destination.
    
- Il ne garantit pas la synchronisation ni l’ordre des données.
    
- Il ne réserve pas de connexion continue entre les deux appareils.
    

## Avantages de l’UDP

- Transmission beaucoup plus rapide que TCP.
    
- Très flexible pour les développeurs, car le contrôle peut être transféré au logiciel applicatif.
    
- Ne monopolise pas une connexion permanente sur la machine.
    

## Inconvénients de l’UDP

- Aucune garantie de réception des données.
    
- Connexion instable = expérience utilisateur médiocre.
    

---

## Quand utiliser TCP ou UDP ?

- TCP est utilisé dans des situations où _l’intégrité_ des données est essentielle : navigation web, messagerie électronique, transfert de fichiers.
    
- UDP est préféré lorsque la _vitesse_ est plus importante que la fiabilité : streaming vidéo, appels VoIP, découverte d’appareils sur un réseau.

layer session

La couche session (couche 5 du modèle OSI) est chargée de **gérer, établir et maintenir les connexions** entre deux ordinateurs. Une fois que les données ont été préparées par la couche présentation (couche 6), la couche session crée une session afin de transporter ces données de manière organisée et contrôlée.

---

## La couche session

- Elle **crée une session** dès qu’une connexion est établie entre deux machines.
    
- Tant que la connexion est active, la session reste ouverte.
    
- Elle est responsable de **la fermeture de la session** lorsqu’elle n’est plus utilisée ou si la connexion est perdue.
    

---

## Caractéristiques et fonctions

- La couche session peut insérer des **points de contrôle** (checkpoints) dans la transmission. Ces points permettent, en cas de perte de données, de ne renvoyer que les parties manquantes depuis le dernier point sauvegardé, ce qui économise de la bande passante.
    
- Chaque **session est unique** : les données ne peuvent circuler qu’à l’intérieur de leur propre session et non pas à travers plusieurs sessions.
    

---

## Exemple concret

- Un appel vidéo utilise une session unique : tant que les deux utilisateurs sont connectés, la couche session maintient la communication et gère le flux.
    
- Si la connexion est interrompue, la couche session est responsable de **fermer la session** et devra en recréer une nouvelle si l’appel reprend.

Layer presentation: