---
order: 2
title: Requêter
---

# Requêter un jeu de donnée ouvert

Il est possible de requêter un jeu de données ouvert sans être authentifié.
Il suffit de faire un GET sur l'url d'un média du jeu de données. Vous trouverez ci-dessous un exemple de requête :

```
curl -v -X GET "https://rudi.bzh/medias/fe3444be-0580-4670-964d-4a9362a9b8c6/7d704403-c1e0-4001-8d19-a9b0dcbc7965/dwnl"
```

L'url d'un média est consultable depuis le portail, dans le détail d'un jeu de données / Informations complémentaires / Sources de données (un bouton vous permet de copier directement l'url).
