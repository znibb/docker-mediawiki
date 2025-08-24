# docker-mediawiki
Hosting MediaWiki using Docker

## First time setup
1. Select `Databse type:` as `MariaDB, MySQL, or compatible`
1. Under `MariaDB/MySQL settings` enter:
    - Database host: `mediawiki-db`
    - Database name: As per `DB_NAME` in your .env file
    - Database username: As per `DB_USER` in your .env file
    - Database password: As per `DB_PASSWD` in your .env file
1. Click `Continue ->` at the bottom
1. `Use the same account as for installation`: **ON**, click `Continue ->`