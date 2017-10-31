FROM churrops/nginx-php7-fpm

ENV GLPI_VERSION=9.2
ENV GLPI_URL=https://github.com/glpi-project/glpi/releases/download/${GLPI_VERSION}/glpi-${GLPI_VERSION}.tgz
ENV FUSION_VERSION=9.2.1.0
ENV FUSION_URL=https://github.com/fusioninventory/fusioninventory-for-glpi/releases/download/glpi9.2%2B1.0/glpi-fusioninventory-${FUSION_VERSION}.tar.bz2

WORKDIR /var/www/html

RUN wget ${GLPI_URL} \
    && tar zxf glpi-${GLPI_VERSION}.tgz \
    && rm -f glpi-${GLPI_VERSION}.tgz \
    && touch /var/www/html/glpi/favicon.ico \
    && chown -R www-data:www-data /var/www/html/ \
    && rm -f /var/www/html/index.nginx-debian.html \
    && rm -f /etc/nginx/sites-available/default \
    && 232  wget https://github.com/fusioninventory/fusioninventory-for-glpi/releases/download/glpi9.2%2B1.0/glpi-fusioninventory-9.2.1.0.tar.bz2
    && tar jxf glpi-fusioninventory-${FUSION_VERSION}.tar.bz2 -C /var/www/html/plugins/ \
    && rm -f glpi-fusioninventory-${FUSION_VERSION}.tar.bz2

COPY files/default /etc/nginx/sites-available/
