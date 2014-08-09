Architecture des fichiers
==================================

Ce fichier décrit la structure des fichiers du service d'interaction. Rappelons que ce service gère les demandes effectuées par les utilisateurs sur l'interface (typiquement affichage de données, modification sur le profil, etc..).

Structure globale de l'application Rails
----------------------------------------

L'application respecte la structure classique de Rails, voir la documentation pour plus de précisions.
Les dossiers des controlleurs, helpers et modèles devront respecter l'arborescence suivante : 

- **Version API**
	- **Univers**
		- **Module**
			- File.rb
			- File.rb


Par exemple, le dossier controllers


- **V1**
	- **Sports**
		- **Dashboard**
			- graph_controller.rb
			- compare_controller.rb
	- **Global**
		- **Users**
			- login_controller.rb
			- profile_controller.rb

Structure des modèles
---------------------

### User ###

- **username** 
- **email** 
- **firstName** 
- **lastName** 
- **cover** : cover picture link
- **addrs** : Array ["192.168.1.2", "193.178.1.45"]
- **apis** : Object with parameters for user's APIs, to complete

*A compléter*