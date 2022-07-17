FROM ubuntu:20.04
ENV TZ=America/La_Paz
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update -y \ 
    && apt-get upgrade -y \ 
    # Instalamos utilidades
    && apt-get install nano -y \ 
    && apt-get install iputils-ping

# Para reiniciar el serivcio no se puede usar service restart, se debe usar lo siguiente (No olivdar tener el archivo  apache2-foreground en el directorio)
COPY apache2-foreground /usr/local/bin/
#RUN chmod +x /usr/local/bin/apache2-foreground
#CMD ["apache2-foreground"]
