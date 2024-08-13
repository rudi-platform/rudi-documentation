---
order: 3
title: Requêter un média d'un jeu de données ouvert
---

# Requêter un média d'un jeu de données ouvert


Il est possible de requêter un jeu de données ouvert dont le média est de type "FILE" ou "SERVICE".

Il faut d'abord s'authentifier avec un des [trois modes disponibles](../_authentification/authentification.md) afin de récupérer un token JWT.

Il faut ensuite effectuer une requête de la forme :

```
curl -kv -XGET -H "Authorization: Bearer <le token  que vous avez récupéré ci-dessus>" "https://rudi.bzh/medias/{IDENTIFIANT DU JEU DE DONNEES}/{IDENTIFIANT DU MEDIA}/{CONTRAT D'INTERFACE}"
```

L'url d'un jeu de données est consultable depuis le portail, dans le détail d'un jeu de données / Informations complémentaires / Sources de données (un bouton vous permet de copier directement l'url) : 

![image](https://github.com/rudi-platform/rudi-documentation/assets/109140019/320150b0-8ef3-455d-b37e-e63269fb88af)

