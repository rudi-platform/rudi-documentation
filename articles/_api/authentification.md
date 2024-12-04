---
order: 2
title: Authentification
---

# Authentification des fournisseurs de données

Les fournisseurs de données pour publier des métadonnées doivent s'authentifier en OAuth2.

Pour cela, il faut :
* Déclarer le fournisseur dans RUDI Portail (µPoviders)
* Déclarer chaque noeud du fournisseur dans RUDI Portail (µPoviders)
* Déclarer les producteurs associés au fournisseur
* A chaque noeud est associé un utilisateur de type _ROBOT_  (µACL). L'utilisateur possède :

  * un client_id sous la forme d'un UUID V4
  * un client_secret

Le noeud fournisseur peut alors s'authentifier comme suit :

```
curl -v --request POST http://<site-rudi>/oauth/token --data "grant_type=password" --data "username=username>" --data "password=password>" --data "scope=liste des scopes séparés par des virgules>" --data "client_id=<client_id>" -H "Authorization:Basic <encodage en base 64 de la chaine client_id:<client_password>"
```


# Contrôle de l'authentification appel du Portail RUDI vers un fournisseur de données

Lorsque le portail vient moissonner des données d'un fournisseur de données ou lorsque le portail vient soumettre un rapport d'intégration, l'appel comporte une entête d'authorization de type "Bearer".

Exemple :
```
Authorization: Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJydWRpIiwiY29ubmVjdGVkVXNlciI6eyJsb2dpbiI6InJ1ZGkiLCJ0eXBlIjoiUEVSU09OIiwiZmlyc3RuYW1lIjoicnVkaSIsImxhc3RuYW1lIjoicnVkaSIsImVtYWlsIjpudWxsLCJvcmdhbml6YXRpb24iOiJydWRpIiwicm9sZXMiOlsiQURNSU5JU1RSQVRPUiJdfSwiZXhwIjoxNjE0NjE5Nzc2LCJpYXQiOjE2MTQ2MTYxNzZ9.Em7yclposciDOll-Dgv9O6jGDE-GsVEHp9dYKyfYNCyPTAambdGqtnl--Zw0DidCf0_JCghXlpznMIteUPdHnQ
```

Le fournisseur de données peut valider ce token en réalisant l'appel suivant vers le portail :

```
curl -v --request GET http://<site-rudi>/oauth/check_token?token=<valeur du token>
```

# Authentification des porteurs de projets

Lorsqu'un porteur de projet souhaite utiliser un jeu de données exposé par le portail, il peut le faire
* soit en tant qu'utilisateur anonyme. Cette possibilité est proposée afin de permettre à un utilisateur de réaliser des essais rapidement
* soit en son nom. C'est le cas de tous les jeux de données à accès restreint et c'est aussi le cas si le porteur de projet souhaite une qualité de service particulière. Il est important de noter que pour effectuer ce mode d'authentification, il est nécessaire de soumettre un projet dans Rudi.
* soit au titre du projet. C'est le case lorsque le porteur de projet souhaite consommer les données depuis une application tierce. 

Les trois modes d'authentification sont disponibles [ici](../_authentification/authentification.md).
