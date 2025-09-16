![[Pasted image 20250916115933.png]]UDP (_User Datagram Protocol_) est un protocole de communication de la couche **transport** du modèle OSI, qui permet d’envoyer des paquets de données entre deux appareils sans établir de connexion préalable. Contrairement à TCP, UDP est _sans état_ et ne garantit pas la livraison, l’ordre ni l’intégrité des données, mais en échange, il est beaucoup plus rapide et léger.

## Caractéristiques principales de l’UDP

- **Stateless (sans état)** : il n’y a pas de “handshake” comme dans TCP, les paquets (appelés _datagrammes_) sont envoyés sans suivi.
    
- **Pas de garantie** : un paquet peut être perdu, dupliqué ou arriver dans le désordre sans que le protocole tente de corriger cela.
    
- **Faible surcharge** : les en-têtes UDP sont beaucoup plus simples et courts que ceux de TCP, ce qui le rend rapide et adapté aux transmissions où la vitesse est plus importante que la fiabilité.
    
- **Souplesse** : c’est l’application qui décide comment gérer la perte ou l’ordre des paquets si nécessaire.
    

## Avantages de l’UDP

- Très rapide (pas de connexion à établir, petits en-têtes).
    
- Léger et peu gourmand en ressources.
    
- Utile pour les applications temps réel (voix, vidéo en streaming, jeux en ligne).
    
- Permet la diffusion (_broadcast/multicast_) à plusieurs hôtes facilement.
    

## Inconvénients de l’UDP

- Pas de garantie de livraison (les paquets peuvent être perdus).
    
- Pas d’assurance d’ordre d’arrivée des paquets.
    
- Si la connexion réseau est instable, l’expérience utilisateur devient très mauvaise.
    

## Principaux champs d’en-tête UDP

- **Source Port** : numéro de port de l’application émettrice.
    
- **Destination Port** : numéro de port de l’application réceptrice (ex. : DNS sur le port 53).
    
- **Longueur** : taille totale du datagramme UDP.
    
- **Checksum** : permet une vérification d’erreur simple (facultatif en IPv4, obligatoire en IPv6).
    
- **Données (payload)** : les informations réellement envoyées.
    

## Exemples d’utilisation

- **Streaming vidéo/audio** (YouTube, appels VoIP, visioconférences).
    
- **Jeux en ligne** (où la réactivité est plus importante que la fiabilité).
    
- **DNS** (Domain Name System), car une question/réponse est très rapide et peut tolérer la perte d’un paquet.
    

En résumé, UDP est choisi quand la rapidité et le temps réel priment sur la fiabilité, contrairement à TCP qui privilégie l’intégrité des données et la fiabilité des communications.