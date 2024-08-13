---
order: 3
title: Accéder aux données en accès restreint
---

# Accéder aux données en accès restreint

Une fois la demande d'accès acceptée par le producteur et la souscription réalisée, vous pouvez accéder au jeu de données de 2 manières :
* soit directement dans le portail de manière similaire aux jeux de données ouverts,
* soit via API.

## Téléchargement de la donnée à partir du portail

Vous pouvez également télécharger le jeu de données depuis son détail : pour cela vous devez vous connecter, accéder au détail du jeu de donnée et cliquer sur le bouton Télécharger.
![restprod](https://user-images.githubusercontent.com/109140019/221825731-2b310847-767f-47f6-a624-8e9a2c99ebae.PNG)


## Téléchargement de la donnée via API

Il faut d'abord s'authentifier avec une des [deux modes disponibles](../_authentification/authentification.md) afin de récupérer un token JWT.

Cet appel permet de récupérer un token.

Il faut ensuite effectuer une requête de la forme :

```
curl -kv -XGET -H "Authorization: Bearer <le token  que vous avez récupéré ci-dessus>" "https://rudi.bzh/medias/{IDENTIFIANT DU JEU DE DONNEES}/{IDENTIFIANT DU MEDIA}/{CONTRAT D'INTERFACE}"
```

L'url d'un jeu de données est consultable depuis le portail, dans le détail d'un jeu de données / Informations complémentaires / Sources de données (un bouton vous permet de copier directement l'url).


