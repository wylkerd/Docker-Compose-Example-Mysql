# DockerCompose-Mysql-And-Postgres

- inside a docker folder at the root of the project add this to the dockercompose.yml file
- On VSCode with Docker extension, execute 'docker compose up' on docker-compose.yml

## Access on Mysql container
- Attach shell
- and use 'mysql -p' for database password

## Access on Postgres container
- Attach shell
- and use 'psql <database name>' for access database
    - use '\dt' for show all tables on database
    - use '\d <table name>' for show table structure 
    
## Connetion in MySQlServer ( Default port: 3306 )
- if necessary run "docker compose up".
```
version: '3.1'

services:
  
  db:
    image: mysql
    container_name: mysql-container
    command: --default-authentication-plugin=mysql_native_password
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: docker
      MYSQL_DATABASE: db_test
    volumes: 
      - /var/lib/mysql
    ports:
      - '8080:3306'
  ```
