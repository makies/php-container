FROM php:8-apache


RUN apt update

RUN apt install -y git zip unzip libzip-dev zlib1g-dev default-mysql-client
RUN git --version

#RUN apt install -y zip
#RUN which zip
#RUN apt install -y unzip


# RUN apt install -y zlib1g-dev
RUN docker-php-ext-install zip
# RUN apt install -y php-zip

# mysql
# RUN apt install -y default-mysql-client
RUN docker-php-ext-install pdo_mysql

# Install composer
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer
ENV COMPOSER_ALLOW_SUPERUSER 1


ADD index.php /var/www/html/index.php