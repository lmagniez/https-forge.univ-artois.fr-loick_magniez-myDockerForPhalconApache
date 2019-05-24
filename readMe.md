
# 0. About the project

The official project phalcon-compose allowing to create easily container with phalcon is no longer maintained. I tried in this project to create a basic docker container containing a lamp instance with phalcon installed.

The project use as a basis the mattrayner/lamp image available at this url:
https://hub.docker.com/r/mattrayner/lamp

The project use the latest-1604-php7 version:
- Apache 	2.4.18
- MySQL 	5.7.23
- PHP 	7.2.9
- phpMyAdmin 	4.8.2

# 1. How to run

## 1.1 Run docker
```
docker-compose up
```
db host&port (mariadb): db:3306

apache2 host&port: phalcon:80

Accès en bash
```
docker exec -it <ContainerId> bash
```

## 1.2 Connect to db from host
```
mysql -h localhost -P 3306 --protocol=tcp -u root -p
```
db login are available and can be changed in docker-compose.yml.

## 1.3 Access to the phalcon app

Url to access the app:
localhost/< appName >/
phaphalcon.com/< appName >/

# 2. How to configure

## 2.1 Insert database script

Script are added automatically to the database.
When executing docker-compose, the db component will execute the script in the docker/maria_db/db_init/1_ddl.sql file.

## 2.2 Insert phalcon app
In phalcon-app folder, insert your phalcon app folder.
A sample project is already included in the project
