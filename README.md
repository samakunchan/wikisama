# Wiki

Contient un fichier ``docker-compose.yml`` afin de construire mon wikijs.<br>
Ce wiki lira les données d'un repository dédié à la documentation qui restera privé pour l'instant.

## Utilisation

Créer les fichiers de variables d'environnment avec les fichiers d'exemple.

```sh
cp .docker-postgres-example.env .docker-postgres.env
```

```sh
cp .docker-wiki-sama-example.env .docker-wiki-sama.env
```

## Construction

```sh
docker-compose up -d
```
