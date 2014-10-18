# Horaires SNCF API



API expérimentale permettant de récupérer les infos pratiques et horaires des trains au départ ou à l'arrivée disponibles pour plus de 800 gares françaises.

## Adresse de l'API
```
http://api-sncf.davidsan.fr
```

L'API est de type REST et renvoie les informations au format JSON.

## Limitations
Le serveur est hébergé par Heroku sur un dyno standard avec un forfait "free-tier".
Les limitations applicables sont donc celles d'Heroku pour l'exécution d'un dyno standard. 

**Cette API ne doit pas être utilisé en production !**

## Origine des données
Les données distribuées par l'API sont celles disponibles à travers le site de la SNCF. Elles sont identiques à celles qui sont affichées sur le site de la SNCF.

## Requête /station/

  Retourne un JSON contenant des informations sur la station, la liste des prochains départs de train, et la liste des prochaines arrivées de train en gare.

* **URL**

  /station/`code`

* **Method:**

  `GET`

* **Success Response:**

  * **Sample of [/station/FRPST](http://api-sncf.davidsan.fr/station/FRPST)** 
  
```
{
   code:"FRPST",
   name:"Paris Est",
   displayName: "Gare de Paris Est ",
   address:"Place du 11 novembre 1918 75475 Paris",
   latitude:"48.877552",
   longitude:"2.359156",
   departures:[
      {
         brand:"INTERCITES",
         num:"11941",
         time:"20:42",
         destination:"CULMONT CH",
         platform:"24",
         state:"À L'Heure"
      },
      {
         brand:"TGV",
         num:"2521",
         time:"21:06",
         destination:"NANCY",
         platform:"--",
         state:"À L'Heure"
      },
      {
         brand:"TGV",
         num:"2765",
         time:"21:22",
         destination:"SEDAN",
         platform:"--",
         state:"À L'Heure"
      }
   ],
   arrivals:[
      {
         brand:"TGV",
         num:"2876",
         time:"20:23 Delayed 10MIN",
         destination:"LUXEMBOURG",
         platform:"5",
         state:"Retard 25MIN"
      },
      {
         brand:"ELIPSOS",
         num:"452",
         time:"20:24 Arrived",
         destination:"MOSCOU",
         platform:"25",
         state:"Arrivé"
      },
      {
         brand:"TGV",
         num:"2762",
         time:"20:35",
         destination:"REIMS",
         platform:"29",
         state:"À L'Heure"
      }
   ]
}
``` 
La liste des codes de gare est accessible dans le fichier station.md.

### Droits des données

Toutes les données appartiennent à la Société Nationale des Chemins de fer Français SNCF et ne sont pas utilisées à des fins de commerce.

### Droits d'utilisation de cette API

Cette API est réservée à un usage strictement personnel.

