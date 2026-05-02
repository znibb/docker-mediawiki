# docker-mediawiki
Hosting MediaWiki using Docker behind a Traefik reverse-proxy

## Docker setup
1. Initialize config by running init.sh: `./init.sh`
1. Input personal information into `.env`
1. Make sure that Docker network `traefik` exists, `docker network ls`
1. Make sure that the volume entry for `LocalSettings.php` is commented out, this file will be generated on initial container startup
1. Run `docker compose up -d` and go to `<LOCAL_SERVER_IP>:8080` and follow the installation procedure
1. Select `Database type:` as `MariaDB, MySQL, or compatible`
1. Under `MariaDB/MySQL settings` enter:
    - Database host: `mediawiki-db`
    - Database name: As per `DB_NAME` in your .env file
    - Database username: As per `DB_USER` in your .env file
    - Database password: As per `DB_PASSWD` in your .env file
1. Click `Continue ->` at the bottom
1. `Use the same account as for installation`: **ON**, click `Continue ->`
1. Save the generated `LocalSettings.php` next to `docker-compose.yml`
1. Take down the stack: `docker compose down`
1. Uncomment the volume entry for `LocalSettings.php`
1. Run `docker compose up -d` and check logs

## Short URLs
If you wanto to enable shorter URLs add the following somewhere in `LocalSettings.php`:
```
$wgArticlePath = "/$1";
$wgUsePathInfo = true;
```

## Site administration
https://www.mediawiki.org/wiki/Manual:CreateAndPromote.php