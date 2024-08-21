---
order: 3
title: Média WMS
---

# Publier un jeu de données ayant un média de type WMS

Vous trouverez ci-dessous la section *available_formats* à ajouter à votre json de publication afin de publier un media de type WMS.

```
"available_formats": [
        {
            "media_type": "SERVICE", //Correspond au type de media, ici il s'agit d'un service (ne pas changer)
            "media_id": "{{$guid}}",//Correspond à l'uuid du media
            "connector": {
                "interface_contract": "wms", //Correspond au type de service (ne pas changer)
                "url": "https://public.sig.rennesmetropole.fr/geoserver/pnat_hab/wms",// Corresopnd au début d'une url récupérée sur un geoserver, ici nous nous arrêterons à "wms"
                "connector_parameters": [
                    {
                        "key": "layer", //Correspond à la clé "layer" (ne pas changer)
                        "value": "pnat_hab:delaisse_urbain", // Correspond à la layer à afficher et renseignée dans url
                        "type": "STRING", //Correspond au format (ne pas changer)
                        "usage": "Nom du layer à récupérer",//Correspond à l'usage de la clé "layer"  (ne pas changer)
                        "accepted_values": [
                            {
                                "cle": "layer" //Correspond à la clé "layer" (ne pas changer)
                            }
                        ]
                    },                    {
                        "key": "versions", //Correspond à la clé "Versions" (ne pas changer)
                        "value": "1.1.0",//Correspond à la version (cette information est à récupérer au sein de l'url affichée dans votre onglet geoserver)
                        "type": "STRING", //Correspond au format  (ne pas changer)
                        "accepted_values": [
                            {
                                "cle": "versions"  //Correspond à la clé "Versions" (ne pas la changer)
                            }
                        ]
                    },
                    {
                        "key": "default_crs", //Correspond à la clé "Default_crs" (ne pas changer)
                        "value": "EPSG:2154", //Correspond au système de projection
                        "type": "STRING", // Correspond au format (ne pas changer)
                        "accepted_values": [
                            {
                                "cle": "default_crs" //Correspond à la clé utilisée "Default_crs" (ne pas changer)
                            }
                        ]
                    },
                    {
                        "key": "formats", //Correspond à la clé "Formats" (ne pas changer)
                        "value": "image/png", //Correspond au format du média (ne pas changer)
                        "type": "STRING", //Correspond au format (ne pas changer)
                        "accepted_values": [
                            {
                                "cle": "formats" //Correspond à la clé "format" (ne pas changer) 
                            }
                        ]
                    }
                ]
            }
        }
    ],
```
