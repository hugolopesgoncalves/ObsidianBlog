![[Pasted image 20250911120141.png]]

- **Couche 1 - Physique** : Cette couche transmet les bits bruts sur un support physique comme des câbles ou ondes. Elle s’occupe des aspects électriques, optiques ou radio, et de la vitesse de transmission.
    
- **Couche 2 - Liaison de données** : Elle organise les bits en trames, gère les adresses physiques (MAC), contrôle les erreurs et le flux pour assurer une transmission fiable entre deux nœuds.
    
- **Couche 3 - Réseau** : Cette couche s’occupe du routage des paquets entre différents réseaux à l’aide d’adresses logiques (IP), en déterminant le chemin optimal pour les données.
    
- **Couche 4 - Transport** : Elle assure la communication fiable entre les systèmes sources et destinations, gérant la segmentation des données, le contrôle de flux et la correction d’erreurs (ex. TCP).
    
- **Couche 5 - Session** : Elle établit, maintient et termine les connexions (sessions) entre applications sur deux machines, gérant les dialogues et synchronisations.
    
- **Couche 6 - Présentation** : Cette couche traduit, compresse et crypte les données pour qu’elles soient compréhensibles par l’application, assurant une représentation cohérente entre systèmes.
    
- **Couche 7 - Application** : C’est l’interface directe avec l’utilisateur et les applications réseau. Elle fournit des services comme le courrier électronique, la navigation web et le transfert de fichiers.


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

La couche 6 du modèle OSI, appelée couche présentation, assure plusieurs fonctions clés pour que les données soient manipulées de manière uniforme et sécurisée entre applications différentes.

---

## Fonctions principales de la couche présentation

- Elle agit comme un **traducteur** de données entre la couche application (couche 7) et la couche session (couche 5). Elle transforme les données de manière à ce que les systèmes avec des formats différents puissent les comprendre. Par exemple, convertir un texte d’un code ASCII à EBCDIC.
    
- Elle effectue la **compression des données** afin de réduire la taille des informations envoyées, ce qui optimise la bande passante et accélère la transmission.
    
- Elle gère le **chiffrement et déchiffrement des données** pour assurer la sécurité pendant leur transfert. C’est à ce niveau que s’appliquent des protocoles tels que SSL/TLS, utilisés pour sécuriser les sites web en HTTPS.
    
- Elle prend en charge la **normalisation de la syntaxe et des formats** (exemples : formats JPEG, MPEG pour images et vidéos).
    

---

## En résumé

On peut voir la couche présentation comme un **interprète** qui garantit que chaque application reçoit des données dans un format qu’elle comprend, tout en assurant leur confidentialité et en optimisant leur taille pour une transmission efficace.

Par exemple, lorsqu’un mail est envoyé, peu importe le client mail utilisé par le destinataire, le contenu sera présenté correctement grâce aux fonctions de cette couche. De même, la sécurité HTTPS est assurée en partie au niveau de cette couche par le chiffrement des données.

---

Si besoin, un résumé simplifié ou une métaphore pédagogique peuvent être proposés pour mieux retenir ce concept complexe.

layer application 

La couche application (couche 7 du modèle OSI) est la couche la plus proche de l’utilisateur final. C’est elle qui fournit les **protocoles et règles** permettant aux utilisateurs d’interagir avec les données envoyées et reçues sur le réseau.

---

## Rôle de la couche application

- Elle sert d’interface directe entre les utilisateurs et le réseau à travers des **applications** comme les clients email, navigateurs web, ou logiciels d’accès à des serveurs de fichiers.
    
- Elle détermine comment les utilisateurs accèdent aux services réseau et manipulent les données.
    
- C’est à ce niveau que fonctionnent de nombreux protocoles essentiels tels que :
    
    - HTTP (navigation web)
        
    - FTP (transfert de fichiers)
        
    - SMTP (envoi d’emails)
        
    - DNS (traduction des noms de domaine en adresses IP)
        

---

## Exemple concret

- Quand un utilisateur tape une adresse web dans un navigateur, la couche application gère la demande, utilise DNS pour traduire ce nom en adresse IP, puis récupère les pages web via HTTP ou HTTPS.
    
- Les logiciels comme FileZilla permettent d’explorer ou transférer des fichiers sur un serveur via FTP, toujours grâce aux protocoles de cette couche.
    

---

