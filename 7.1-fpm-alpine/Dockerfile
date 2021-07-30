FROM php:8.0.9-fpm-alpine

# https://laravel.com/docs/5.8/installation
RUN \
# BCMath PHP Extension
	docker-php-ext-install bcmath; \
# Ctype PHP Extension
# JSON PHP Extension
# Mbstring PHP Extension
# OpenSSL PHP Extension
# PDO PHP Extension
	docker-php-ext-install pdo_mysql;
# Tokenizer PHP Extensions
# XML PHP Extension

# Others
RUN \
# mcrypt
	apk add --no-cache \
		libmcrypt-dev \
	; \
	docker-php-ext-install -j$(getconf _NPROCESSORS_ONLN) mcrypt; \
	# apk del \
	# 	libmcrypt-dev \
	# ; \
# gd
# https://github.com/docker-library/php/issues/225#issuecomment-226870896
	apk add --no-cache \
		freetype \
		libpng \
		libjpeg-turbo \
		freetype-dev \
		libpng-dev \
		libjpeg-turbo-dev \
	; \
	docker-php-ext-configure gd \
		--with-gd \
		--with-freetype-dir=/usr/include/ \
		--with-png-dir=/usr/include/ \
		--with-jpeg-dir=/usr/include/ \
	; \
	docker-php-ext-install -j$(getconf _NPROCESSORS_ONLN) gd; \
	apk del \
		freetype-dev \
		libpng-dev \
		libjpeg-turbo-dev
