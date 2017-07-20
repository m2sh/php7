# PHP7-FPM
[![Docker Pulls](https://img.shields.io/docker/pulls/m2sh/php7.svg?maxAge=2592000?style=flat-square)](https://hub.docker.com/r/m2sh/php7/)  

PHP7 docker image with useful extensions: 
- zip
- intl
- soap
- mysqli
- pdo pdo_mysql pdo_pgsql
- gd
- mcrypt
- iconv
- gmp
- redis
- apcu
- xdebug (available on [`m2sh/php7:alpine-dev`](https://github.com/m2sh/php7/blob/master/alpine/dev/Dockerfile))
- imagick
- mysql-client \[`mysqldump`\] (available on [`m2sh/php7:alpine-mysql`](https://github.com/m2sh/php7/blob/master/alpine/mysql/Dockerfile))
- bcmath (required by hashids package)

Tags & Dockerfiles:  
based on `php:7-fpm` (debian based php image):  
- `latest` - (`~275MB`) [(Dockerfile)](https://github.com/m2sh/php7/blob/master/Dockerfile)
- `light`  - (`~275MB`) - [(light/Dockerfile)](https://github.com/m2sh/php7/blob/master/light/Dockerfile)   

based on `php:7-fpm-alpine` (alpine based php image):  
- `alpine` - (`~52MB`) [(alpine/Dockerfile)](https://github.com/m2sh/php7/blob/master/alpine/Dockerfile)
