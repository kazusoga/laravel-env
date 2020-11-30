FROM php:7.2-apache
RUN apt-get update && \
     apt-get install -y \
         libzip-dev \
         && docker-php-ext-install zip pdo_mysql mysqli mbstring \
         && a2enmod rewrite
COPY --from=composer /usr/bin/composer /usr/bin/composer
RUN composer global require "laravel/installer" && echo 'export PATH=$HOME/.composer/vendor/bin:$PATH' >> ~/.bashrc
