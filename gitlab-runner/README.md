## Activer un gitlab-runner

1. Enregistrer

    ```sh
    $ cd ./gitlab-runner
    $ docker-compose run --rm -v $PWD/config/gitlab-runner:/etc/gitlab-runner gitlab-runner register
    ```

2. Eventuellement raffiner la configuration : dans config/gitlab-runner/config.toml

3. Puis lancer le service :

    ```sh
    $ docker-compose up -d gitlab-runner
    ```

    Remarque : le service recharge sa configuration à chaud, aucun redémarrage n'est nécessaire après un changement
