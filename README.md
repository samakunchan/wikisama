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

## Synchronisation github

Dans `Storage`:
- Authentication Type: `Basic` (IMPORTANT)
- Repository Uri : `https://github.com/samakunchan/documentation`
- Branch : `main`
- SSH Private Key Mode : `path`
- (vide)
- (vide)
- Username : `samakunchan`
- Password / PAT : `ghp_xxxxxx`
- Default Author Email : `cedric.badjah@gmail.com`
- Default Author Name : `Samakunchan`

## Synchronisation keycloak
Pour configurer l'authentification avec Keycloak de wikijs
- Host : `https://secure-connect.devpapangue.com`
- Realm : ppg-connect
- Client ID : documentation
- Client Secret : Fournis pas keycloak
- Authorization Endpoint Url : `https://secure-connect.devpapangue.com/realms/ppg-connect/protocol/openid-connect/auth`
- Token Endpoint Url : `https://secure-connect.devpapangue.com/realms/ppg-connect/protocol/openid-connect/token`
- User Info Endpoint Url : `https://secure-connect.devpapangue.com/realms/ppg-connect/protocol/openid-connect/userinfo`
- Logout Endpoint Url : `https://secure-connect.devpapangue.com/realms/ppg-connect/protocol/openid-connect/logout`
- **Autoriser l'auto-inscription**
- **Créer un groupe afin d'ajouter les utilisateurs utilisant cette authentification à un groupe.***

NB : en bas de page, il y a des infos à mettre dans Keycloak comme le redirect_uri (ex : `https://documentation.devpapangue.com/login/xxx-xxx-xxx/callback`)
