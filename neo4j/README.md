# Neo4J stack

## Variables custom

Dans le fichier `docker-compose.yml` sont définies des variables d'environnement personnalisées
que l'on devra définir selon ses propres besoins :

- `NEO4J_ADMIN_USERNAME` : Nom de l'utilisateur admin Neo4J

- `NEO4J_ADMIN_PASSWORD` : Mot de passe de l'utilisateur admin Neo4J

## Utilisation

Une fois le conteneur lancé, aller sur le browser Neo4J (http://localhost:7474). Pour se connecter à Neo4J, l'interface doit être paramétrée comme suit : 

- `Connect URL` : `neo4j://localhost:7687`

- `Database` : Nom de la base, si c'est la première connexion, laisser vide

- `Username` : Contenu de la variable d'environnement `NEO4J_ADMIN_USERNAME` avec laquelle le conteneur a été créé

- `Password` : Contenu de la variable d'environnement `NEO4J_ADMIN_PASSWORD` avec laquelle le conteneur a été créé

## Sources

[Neo4J sur Docker Hub](https://hub.docker.com/_/neo4j)

[Doc Neo4J sur Docker](https://neo4j.com/developer/docker-run-neo4j/)

[Documentation Neo4J](https://neo4j.com/docs/)
