FROM php:7.2-apache
RUN apt-get update -y \ 
    && apt-get upgrade -y \ 
    && apt-get install nano -y \ 
    && apt-get install iputils-ping -y \
    && a2enmod rewrite \
    && service apache2 restart
