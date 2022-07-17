FROM ubuntu:20.04
ENV TZ=America/La_Paz
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update -y \ 
    && apt-get upgrade -y \ 
    # Instalamos utilidades
    && apt-get install nano -y \ 
    # Instalamos apache
    && apt-get install apache2 -y \
    && echo "ServerName localhost" >> /etc/apache2/apache2.conf \
    # Instalamos php
    && apt-get install php -y\
    # Instalamos el driver para conectar php y mysql
    && apt-get install php-mysql -y \
    # Instalamos el driver para conectar php y postgresql
    && apt-get install php-pgsql -y \
    # Habilitamos rewrite para leer el htaccess de cada sitio web
    && a2enmod rewrite \ 
    # Instalamos las librerias para usar Snappy como generador de pdfs
    && apt-get install fontconfig -y\
    && apt-get install libxrender1 -y\
    && apt-get install libxtst6 -y
# Para reiniciar el serivcio no se puede usar service restart, se debe usar lo siguiente (No olivdar tener el archivo  apache2-foreground en el directorio)
COPY apache2-foreground /usr/local/bin/
RUN chmod +x /usr/local/bin/apache2-foreground
CMD ["apache2-foreground"]
