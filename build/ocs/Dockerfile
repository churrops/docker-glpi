FROM churrops/nginx-php7-fpm

ENV OCS_VERSION="2.4"

ENV OCS_URL="https://github.com/OCSInventory-NG/OCSInventory-ocsreports/releases/download/2.4/OCSNG_UNIX_SERVER_${OCS_VERSION}.tar.gz"

WORKDIR /var/www/html

RUN wget ${OCS_URL} \
    && tar zxf OCSNG_UNIX_SERVER_${OCS_VERSION}.tar.gz \
    && mv OCSNG_UNIX_SERVER_${OCS_VERSION}/ocsreports/* /var/www/html/ \
    && rm -f OCSNG_UNIX_SERVER_${OCS_VERSION}.tar.gz \
    && touch /var/www/html/favicon.ico \
    && rm -f /var/www/html/index.nginx-debian.html \
    && rm -f /etc/nginx/sites-available/default \
    && apt-get update -y && apt-get install php7.0-soap bzip2 -y && rm -rf /var/lib/apt/lists/* \
    && chown -R www-data:www-data /var/www/html/

COPY files/default /etc/nginx/sites-available/
