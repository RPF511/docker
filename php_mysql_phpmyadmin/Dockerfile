FROM php:7.1.2-apache 

RUN apt-get install libmcrypt-dev
RUN apt-get install -y git zip
RUN apt-get install -y libssl-dev openssl
#RUN apt-get update && apt-get install -y libmcrypt-dev
RUN apt-get update && apt-get install -y vim
RUN apt-get update && apt-get install -y mysql-client
RUN docker-php-ext-install mcrypt && docker-php-ext-enable mcrypt
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install pdo pdo_mysql
RUN docker-php-ext-install sockets
RUN docker-php-ext-install phar

RUN a2enmod rewrite
RUN a2enmod headers
RUN apache2ctl -k graceful

EXPOSE 80