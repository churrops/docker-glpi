FROM churrops/nginx-php7-fpm

ENV GLPI_VERSION=9.2
ENV GLPI_URL=https://github.com/glpi-project/glpi/releases/download/${GLPI_VERSION}/glpi-${GLPI_VERSION}.tgz

WORKDIR /var/www/html

RUN wget ${GLPI_URL} \
    && tar zxf glpi-${GLPI_VERSION}.tgz \
    && rm -f glpi-${GLPI_VERSION}.tgz \
    && touch /var/www/html/glpi/favicon.ico \
    && chown -R www-data:www-data /var/www/html/ \
    && rm -f /var/www/html/index.nginx-debian.html \
    && rm -f /etc/nginx/sites-available/default

COPY files/glpi /etc/nginx/sites-available/
