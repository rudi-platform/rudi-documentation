---
order: 4
title: Média WFS
---

# Publier un jeu de données ayant un média de type WFS

Vous trouverez ci-dessous la section *available_formats* à ajouter à votre json de publication afin de publier un media de type WFS.


```
"available_formats": [
        {
            "media_type": "SERVICE", //Correspond au type de media, ici il s'agit d'un service (ne pas changer)
            "media_id": "{{$guid}}", //Correspond à l'uuid du media
            "connector": {
                "interface_contract": "wfs", //Correspond au type de service (ne pas changer)
                "url": "https://public.sig.rennesmetropole.fr/geoserver/eq_cultspo/ows", // Correspond au début d'une url récupérée sur un geoserver, ici nous nous arrêterons à "ows"
                "connector_parameters": [
                    {
                        "key": "layer", //Correspond à la clé utilisée (ne pas changer)
                        "value": "eq_cultspo:v_sport_proximite", // Correspond à la layer à afficher
                        "type": "STRING", //Correspond au format (ne pas changer) 
                        "usage": "Nom du layer à récupérer", //Correspond à l'usage de la clé (ne pas changer)
                        "accepted_values": [
                            {
                                "cle": "layer" //Correspond à la clé utilisée (ne pas changer)
                            }
                        ]
                    },
                                        {
                        "key": "versions",//Correspond à la clé "Versions" (ne pas changer)
                        "value": "1.0.0", //Correspond à la version (cette information est à récupérer au sein de l'url affichée dans votre onglet geoserver)
                        "type": "STRING",
                        "accepted_values": [
                            {
                                "cle": "versions" //Correspond à la clé "Versions" (ne pas changer)
                            }
                        ]
                    },
                    {
                        "key": "default_crs",//Correspond à la clé "default_crs" (ne pas changer)
                        "value": "EPSG:3857",//Correspond au système de projection
                        "type": "STRING",
                        "accepted_values": [
                            {
                                "cle": "default_crs"//Correspond à la clé utilisée (ne pas changer)
                            }
                        ]
                    },
                    {
                        "key": "formats", //Correspond à la clé "formats" (ne pas changer)
                        "value": "application/json", //Correspond au format (ne pas changer)
                        "type": "STRING", //Correspond au format  (ne pas changer)
                        "accepted_values": [
                            {
                                "cle": "formats"//Correspond à la clé "formats"  (ne pas changer)
                            }
                        ]
                    }
                ]
            }
        }
    ],

```
