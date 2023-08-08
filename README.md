Firio docker environment
================================

Set up local environment

Prerequisite
You must have installed Docker (https://docs.docker.com/get-docker/) and Docker compose (https://docs.docker.com/compose/install/).

== GIT
Clone Docker env from GIT
- git clone git@github.com:FirioSolutions/firio-docker-env.git

Open "firio-docker-env" folder
- cd firio-docker-env

Clone ContentArena from GIT
- git clone git@github.com:fitchmario/videocourses.git

== DATABASE
Change "docker-compose.yml" params according to app requests
- "MYSQL_ROOT_PASSWORD"={firio-db-root-password}
- "MYSQL_DATABASE"={firio-db-name} # set: app

Creating database with data
- Download file https://drive.google.com/file/d/1MsRCtm1CFg2ULqxWxXhZUPzut0WsUNFu/view?usp=sharing and extract data to "./ca-docker-env/data/mysql"

Change .env params
DATABASE_HOST=mysql
DATABASE_PORT=3306
DATABASE_NAME=app
DATABASE_USER=root
DATABASE_PASSWORD={firio-db-root-password}

== ENVIRONMENT
Put following code in file "/etc/hosts", use "sudo"
- 127.0.0.1 videocourses.local.com pma.local.com

To open PMA, open link
- pma.local.com

To open App, open link
- videocourses.local.com

== START DOCKER
Start docker env
- docker-compose up -d

List dockers
docker ps

== APP DEPEDENCY INSTALATION
Install Symfony dependecies
- Connect to PHP container "docker exec -it firiodev_php_1 sh"
- composer install
