Normes et règles de conception API
==================================

Documentation concernant le développement des API. Toute modification/création doit scrupuleusement respecter les normes prescrites ci-dessous.
Toute demande de modification doit faire l'object d'une pull request.

Réponses
---------------

Les API communiquent entre elles et avec le client en JSON. La structure de conception des méthodes de l'API est libre, ainsi l'appréciation de la gestion des erreurs et des objets retournés est laissé au développeur.

Cependant, la réponse finale doit obligatoirement contenir les éléments suivants

- **Un code HTTP valide** : Choisissez judicieusement : [Liste des codes][1]

- **Un tableau d'erreurs**, retournez un tableau vide s'il n'y a pas d'erreur
```
    { 
        "errors" : []
    }
```
Chaque erreur doit posséder au minimum un code unique, un type et un message. Une description peut être ajoutée en cas d'erreur particulière (pour le développeur essentiellement).
```
    { 
        "errors" : [
            {
                "code": 1234,
                "type" : "Parameter",
                "message" : "Missing parameter user_id",
                "description" : "
            }
        ]
    }
```

N'enveloppez pas systématiquement les données retournées, seulement si c'est absolument nécessaire.

Par exemple, évitez ça :
```
    {   
        "errors": [],
        "data" : {
            "user" {
                "id": 1234,
                "username" : "Stark",
                "email" : "stark@stark.com",
                "description" : "I'm the CEO bitches"
            }
        }
    }
```
Préférez ça :
```
    { 
        "errors": [],
        "user" {
            "id": 1234,
            "username" : "Stark",
            "email" : "stark@stark.com",
            "description" : "I'm the CEO bitches"
        }
    }
```

Les deux seuls raisons d'envelopper les données sont les suivantes : 

- Support des requêtes cross domaines avec JSONP
- Le client ne peut traiter les entêtes HTTP


  [1]: http://fr.wikipedia.org/wiki/Liste_des_codes_HTTP