## Que fait nslookup ?

nslookup est un outil en ligne de commande permettant d’interroger le système DNS afin d’obtenir des informations sur un nom de domaine, par exemple ses adresses IP, ses alias (CNAME), ses clés de mail (MX), etc. Il aide à diagnostiquer et vérifier la configuration DNS d’un domaine.

## Explication des commandes et des résultats

- `nslookup --type=CNAME shop.website.thm`  
    Interroge le type d’enregistrement CNAME (alias) pour shop.website.thm. Résultat : il pointe vers shops.myshopify.com, donc shop.website.thm est un alias pour ce service.  
    **Vocabulaire** :
    
    - **CNAME** : Canonical Name, permet de faire pointer un nom de domaine vers un autre.
        
- `nslookup --type=TXT website.thm`  
    Interroge le type TXT pour website.thm, souvent utilisé pour la vérification, le SPF, ou d’autres informations texte.  
    Résultat : la valeur retournée est une chaîne unique qui pourrait servir à vérifier un domaine.  
    **TXT** : champ texte libre associé au domaine.
    
- `nslookup --type=MX website.thm`  
    Cherche les serveurs de mail (Mail eXchanger), retourne ici une entrée vers alt4.aspmx.l.google.com avec la priorité 30.  
    **MX** : identifie les serveurs gérant les emails pour le domaine.  
    **Priority** : plus la valeur est basse, plus la priorité est haute ; ici 30, c’est donc un serveur de secours (les plus importants ont priorité 10, 20…).
    
- `nslookup www.website.thm`  
    Par défaut, nslookup interroge le type A (adresse IPv4). Résultat : 10.10.10.10  
    **A record** : donne l’adresse IP v4 associée à un nom de domaine.
    

## Résumé du vocabulaire

|Terme|Définition|
|---|---|
|nslookup|Outil CLI pour interroger le DNS|
|CNAME|Alias d’un nom de domaine|
|TXT|Enregistrement texte, pour vérification/infos|
|MX|Serveur de messagerie, avec une priorité|
|A|Adresse IPv4 du domaine|
|Priority|Ordre/importance d’un serveur MX|

## Fonctionnement

À chaque commande, nslookup envoie une requête DNS de type spécifique (CNAME, TXT, MX, A) vers le serveur DNS configuré (ici, 127.0.0.53), qui renvoie la réponse correspondante, affichée sous forme lisible à l’écran. C’est un outil essentiel en administration réseau pour toute opération de debug ou de compréhension des mécanismes DNS.