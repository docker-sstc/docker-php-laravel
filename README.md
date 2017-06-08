# docker-php-laravel [![Docker Build Statu](https://img.shields.io/docker/build/sstc/php-laravel.svg)](https://hub.docker.com/r/sstc/php-laravel/)

php dependencies installed for Laravel 5

## Usage

```sh
docker run \
-d \
--name app \
-p 80:80 \
-v `pwd`:/var/www/html \
sstc/php-laravel:apache
```
