---
order: 3
title: API exposées
---

Le portail Rudi expose des microservices pour sa propre utilisation mais ils peuvent également être utilisés par tous en s'authentifiant ou non.

# Microservices exposés par le portail Rudi

Les microservices exposés sont listés ci-dessous. Leur documentation est accessible via les hyperliens.

* *https:// <site-rudi> /acl/swagger-ui.html* : microservice permettant d'administrer les utilisateurs
* *https:// <site-rudi> /konsult/swagger-ui.html* : microservice permettant d'administrer les jeux de données du catalogue Rudi
* *https:// <site-rudi> /projekt/swagger-ui.html* : microservice permettant d'administrer les projets dans Rudi
* *https:// <site-rudi> /kos/swagger-ui/index.html?configUrl=%2Fkos%2Fv3%2Fapi-docs%2Fswagger-config&urls.primaryName=kos : microservice permettant d'administrer les mots-clés et thèmes au format SKOS
* *https:// <site-rudi> /kalim/swagger-ui.html* : microservice permettant de publier/modifier/supprimer un jeu de données dans le portail
* *https:// <site-rudi> /strukture/swagger-ui.html* : microservice permettant d'administrer les producteurs de données

# API de catalogage des jeux de données

Le microservice konsult expose une API de catalogage des jeux de données Rudi (*https://<site-rudi>/konsult/swagger-ui/index.html?configUrl=%2Fkonsult%2Fv3%2Fapi-docs%2Fswagger-config&urls.primaryName=konsult#/datasets/searchMetadatas*).


Pour l'utiliser, il est nécessaire de s'authentifier au près du portail en tant qu'anonymous ou avec votre compte utilisateur et de récupérer un access token  Rudi :

```
curl -v -X POST "https://<site-rudi>/authenticate" --header "Content-Type: application/x-www-form-urlencoded" --data-urlencode "login=anonymous" --data-urlencode "password=anonymous"
```

A partir du token il est alors possible de requêter l'API de catalogage comme suit :

```
curl -v -X GET  "https://<site-rudi>/konsult/v1/datasets/metadatas" -H "Authorization: Bearer [l'access token retourné par l'appel précédent]"
```

# API pour récupérer la clé publique de chiffrement

Le micoservice konsult expose une API permettant de récupérer la clé publique pour chiffrer les données *https://<site-rudi>/konsult/swagger-ui/index.html?configUrl=%2Fkonsult%2Fv3%2Fapi-docs%2Fswagger-config&urls.primaryName=konsult#/encryption-key/getEncryptionKey*.

La clé publique est récupérable de la manière suivante :
```
curl -X GET "https://<site-rudi>/konsult/v1/encryption-key" -H  "accept: application/octet-stream"
```  
