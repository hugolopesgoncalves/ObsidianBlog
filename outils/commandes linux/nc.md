La commande **nc** (pour **netcat**) dans le terminal permet d’ouvrir, de lire et d’écrire des données à travers le réseau, en utilisant TCP ou UDP, directement depuis la ligne de commande.[linuxtricks+2](https://www.linuxtricks.fr/wiki/nc-netcat-la-boite-a-outils-reseau)

## Utilisations principales de nc

- Établir une connexion à un hôte distant sur un port spécifique (comme un client).[doc.fedora-fr](https://doc.fedora-fr.org/wiki/Netcat,_connexion_client/serveur_en_bash)
    
- Écouter sur un port pour recevoir des connexions (comme un serveur).[lorenzon+1](https://www.lorenzon.ovh/debuter-netcat.html)
    
- Transférer des fichiers entre deux machines via le réseau.[hackernoon](https://hackernoon.com/lang/fr/le-guide-ultime-pour-ma%C3%AEtriser-nmap-et-netcat)
    
- Scanner des ports pour détecter les services actifs sur une machine.[stephane-robert](https://blog.stephane-robert.info/docs/securiser/reseaux/analyse/netcat/)
    
- Tester et déboguer des applications réseau grâce à son fonctionnement simple et flexible.[it-connect+1](https://www.it-connect.fr/a-la-decouverte-de-lutilitaire-netcat-sur-linux/)
    

## Exemples de commandes courantes

- Écouter sur le port 12345 :  
    `nc -l 12345`  
    (Attente de connexion sur le port 12345)
    
- Se connecter à une machine sur le port 12345 :  
    `nc adresse_ip 12345`  
    (Connexion à l’hôte et au port spécifiés)
    
- Scanner des ports sur une machine distante :  
    `nc -zv adresse_ip 20-80`  
    (Test des ports de 20 à 80 et affiche le résultat)
    
- Transférer un fichier :  
    `nc -l 1234 > fichier.txt` (sur la machine réceptrice)  
    `nc adresse_ip 1234 < fichier.txt` (sur la machine source).