FROM php:7.4.29-apache

ENV APACHE_DOCUMENT_ROOT /srv/www/htdocs
ENV APACHE_UID 1000
ENV APACHE_GID 1000


RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf
#changing  USER and group
#ENTRYPOINT  /bin/sh -c
CMD usermod -u ${APACHE_UID} www-data && groupmod -g ${APACHE_UID} www-data && apache2-foreground
