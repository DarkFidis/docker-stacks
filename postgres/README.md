# Stack PostgreSQL

## Variables custom

Dans le fichier `docker-compose.yml` sont définies des variables d'environnement personnalisées
que l'on devra définir selon ses propres besoins :

### postgres-server

- `POSTGRES_USER` : Définit le nom du superuser de PostgreSQL

- `POSTGRES_PASSWORD` : Définit le mode de passe du superuser

[En savoir plus](https://hub.docker.com/_/postgres)

### pgAdmin4

- `PGADMIN_DEFAULT_EMAIL`: Définit l'adresse mail du compte administrateur de pgAdmin

- `PGADMIN_DEFAULT_PASSWORD` : Définit le mot de passe du compte administrateur

[En savoir plus](https://www.pgadmin.org/docs/pgadmin4/latest/container_deployment.html)

## Connection à la base avec pgAdmin

Se connecter à l'interface pgAdmin avec les credentials que l'on aura préalablement renseignés dans le fichier docker-compose (`PGADMIN_DEFAULT_EMAIL`/`PGADMIN_DEFAULT_PASSWORD`)
Ensuite, faire un clic-droit sur `Server` à gauche de l'écran puis `Create` -> `Server`. Dans l'onglet `Connection`, remplir les champs nécéssaires.

Pour le champ `Host`, il faut renseigner l'adresse IP du conteneur `postgres-server`. Pour se faire, entrer la commande suivante : 

```shell script
docker inspect postgres-server
```

Cela donne une sortie comme celle-ci : 
```
"Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "NetworkID": "f35dbe66b36cd38673aad6e1278ad33031ef9d5abd34582d4b91955e288f855e",
                    "EndpointID": "2e63ea59e9d0de7526bb02ba29bc0b16bcad51b8963127ad380416d15da994db",
                    "Gateway": "172.17.0.1",
                    "IPAddress": "172.17.0.2",
                    "IPPrefixLen": 16,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "MacAddress": "02:42:ac:11:00:02",
                    "DriverOpts": null
                }
            }
```

Le host à renseigner est la valeur de la clé `IPAddress` soit dans notre exemple `172.17.0.2`

[Lien StackOverflow](https://stackoverflow.com/questions/53610385/docker-postgres-and-pgadmin-4-connection-refused)
