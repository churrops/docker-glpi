FROM churrops/nginx-php7-fpm

ENV GLPI_VERSION=9.1.6

WORKDIR /var/www/html

RUN wget https://github.com/glpi-project/glpi/releases/download/${GLPI_VERSION}/glpi-${GLPI_VERSION}.tgz \
    && tar zxf glpi-${GLPI_VERSION}.tgz \
    && rm -f glpi-${GLPI_VERSION}.tgz \
    && chown -R www-data:www-data /var/www/html/

COPY files/default /etc/nginx/sites-available/
