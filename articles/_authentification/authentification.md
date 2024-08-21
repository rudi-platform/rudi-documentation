---
order: 1
title: S'authentifier 
---

Trois modes d'authentification sont possibles :

* Authentification *anonymous*
* Authentification avec un compte *Rudi*
* Authentification avec un compte *Réutilisation*

L'ensemble des modes permet de récupérer un token JWT signé qui peut être utilisé en tant que token *Authorization* de type *Bearer*.

# Authentification *anonymous*

Le compte *anonymous* est disponible pour tous et permet un accès à certaines fonctionnalités et certains jeux de données.

```
curl -v -X POST "https://<site-rudi>/authenticate" --header "Content-Type: application/x-www-form-urlencoded" --data-urlencode "login=anonymous" --data-urlencode "password=anonymous"
```

# Authentification avec un compte *Rudi*

Si vous avez créer un compte *Rudi* vous disposez d'un login et d'un mot de passe personnel.

Il est alors possible de s'authentifier comme suit :

```
curl -v -X POST "https://<site-rudi>/oauth/token" --header "Content-Type:application/x-www-form-urlencoded" -H "Authorization: Basic <base64(<login>:<mot de passe>)" -k -d "grant_type=password&username=<login>&password=<mot de passse>" 
```

# Authentification avec un compte *Réutilisation*

Lorsque vous avez créé une [réutilisation](../_glossaire/concepts-rudi.md), il est possible depuis le détail de celle-ci de générer des couples *client_id/client_secret* propre chaque réutilisation.

A partir de ces couples il est possible de s'authentifier comme suit :

```
curl -v -X POST "https://<site-rudi>/oauth/token" --header "Content-Type:application/x-www-form-urlencoded" -H "Authorization: Basic <base64(<client_id>:<client_password>)" -k -d "grant_type=password&username=<client_id>&password=<client_password>" 
```
