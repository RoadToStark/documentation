Structure des bases de données
===================

Documentation de la structure des bases de données liées au projet de données. Pour chaque table on liste les objets et les propriétés associées (MongoDB).

Métriques
---------

### Request ###

*Stockage des métriques sur chaque requête client indépendamment de l'utilisateur et des données*

- **startTime** : Date & heure de la requête
- **userAgent** 
- **method** : GET, PUT, POST..
- **endpoint** : /dashboard
- **params** : Object {name : value}
- **clientIP**
- **duration** : Durée de la requête
- **complete** : boolean
- **error** : Si erreur le message est stocké

Users
---------

### User ###

*Stockage des informations sur les utilisateurs*

- **username** 
- **email** 
- **firstName** 
- **lastName** 
- **cover** : cover picture link
- **addrs** : Array ["192.168.1.2", "193.178.1.45"]
- **apis** : Object with parameters for user's APIs, to complete


*Uncomplete*