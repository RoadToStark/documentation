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
