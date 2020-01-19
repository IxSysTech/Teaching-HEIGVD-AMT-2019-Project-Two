# Teaching-HEIGVD-AMT-2019-Project-Two

## Lancer le projet
Le docker-compose à la racine du projet permet de lancer la base de donnée permettant de run les tests Cucumber

En allant dans le dossier deploy-api vous trouverez le docker-compose permettant de lancer la base de données destinée à l'utilisation du déploiement des APIs sur Traefik

Afin de générler le million d'insertion dans la base de données il vous faudra lancer les commandes suivantes dans mysql-dummy-data.

```
python main.py db_flight_dump.sql --rows 1000000 --output ../deploy-api/database/data-flight/flights.sql
python main.py db_user_dump.sql --rows 1000000 --output ../deploy-api/database/data-user/users.sql
```

Afin de lancer le projet il vous faudra lancer la commande suivante en se mettant à la racine pour lancer la base de données destinées aux tests ou dans deploy-api pour la lancer avec beaucoup d'insértion 

```
docker-compose up --build
```
Ainsi les différents éléments de notre infrastructure vont se lancer et se lier. Vous pourrez suite à ça accéder à l'adresse afin d'accéder à l'interface de Traefik, vous pourrez depuis ici utiliser nos APIs
```
http://localhost/api/jwtuser/swagger-ui.html //Permet d'accéder à l'API User
http://localhost/api/application/swagger-ui.html // Permet d'accéder à l'API Flight
```
Afin de lancer les tests il faudra lancer le projet dans Intellij

## Table des matières

[Aspect fonctionnel](https://github.com/IxSysTech/TrainingREST/blob/master/rapport/functional_aspect.md)

[Détail d'implémentation](https://github.com/IxSysTech/TrainingREST/blob/master/rapport/detail.md)

[Test](https://github.com/IxSysTech/TrainingREST/blob/master/rapport/test.md)
