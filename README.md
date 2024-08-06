## TP_Postgis - IdJO_2024

![https://st4.depositphotos.com/36059186/41222/i/450/depositphotos_412220112-stock-photo-paris-france-september-2017-olympic.jpg](https://st4.depositphotos.com/36059186/41222/i/450/depositphotos_412220112-stock-photo-paris-france-september-2017-olympic.jpg)

*Pour la bonne conduite du TP et de sa correction, respecter les noms proposés*.

### Objectifs 

- Se mettre à l'aise avec des actions courantes.
- Produire des requêtes spatiales simples.
- Créer des vues avec des requêtes imbriquées (CTE).

### Consignes

- Créer une base de données postgis **"jo_2024"**.
- Récupérer les données nécessaires sur le [Catalogue Open Data ](https://data.paris2024.org/explore/?sort=modified&exclude.theme=Geodata&flg=fr-fr),
trouver la donnée sur les sites de compétition.
- Nous utiliserons une couche des communes de france métropolitaine (à minima).
- Intégrer les données dans la base en proposant deux méthodes d'intégration différentes (en vrai faite au plus simple), 
afin d'obtenir une table **"commune"** et une tables **"site_compet"**.
- Nous préviligierons de travailler en EPSG:4326 

### Requêtes

Après vous être assuré que vos données soient bien importées (en sql évidemment !),
 effectuez les requêtes suivantes :

- trouver le nombre de sites de compétitions situés à plus de 5 km de la tour Effeil. 
- créer une vue matérialisée qui permet de connaître la distance en km de chaque site à Null Island.
- créer une vue des communes qui accueillent un site de compétition et compter le nombre de site par commune classé dans l'ordre décroissant.
- créer une vue matérialisée qui permet de calculer la distance du site le plus proche avec une requête imbriquée.
