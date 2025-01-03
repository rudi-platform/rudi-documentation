---
order: 3
title: Requêter un média d'un jeu de données ouvert
---

# Requêter un média d'un jeu de données ouvert


Il est possible de requêter un jeu de données ouvert dont le média est de type "FILE" ou "SERVICE".

Il faut d'abord s'authentifier avec un des [trois modes disponibles](../_authentification/authentification.md) afin de récupérer un token JWT.

Il faut ensuite effectuer une requête de la forme :

```
curl -kv -XGET -H "Authorization: Bearer <le token  que vous avez récupéré ci-dessus>" "https://<site rudi>/medias/{IDENTIFIANT DU JEU DE DONNEES}/{IDENTIFIANT DU MEDIA}/{CONTRAT D'INTERFACE}"
```

L'url d'un jeu de données est consultable depuis le portail, dans le détail d'un jeu de données / Informations complémentaires / Sources de données (un bouton vous permet de copier directement l'url) : 

![Request API](/assets/images/open-data/request-api.png)

