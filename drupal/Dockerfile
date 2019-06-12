FROM php:5.6-apache

RUN apt-get update -y && apt-get install -y sendmail libpng-dev

RUN apt-get update && \
    apt-get install -y \
        zlib1g-dev 

RUN docker-php-ext-install mbstring

RUN docker-php-ext-install zip

RUN docker-php-ext-install gd

RUN docker-php-ext-install mysqli
RUN docker-php-ext-install mysql
RUN docker-php-ext-install pdo_mysql
RUN pecl install xdebug-2.5.5
RUN docker-php-ext-enable xdebug

RUN echo 'xdebug.remote_connect_back=1' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_port=9000' >> /usr/local/etc/php/php.ini
RUN echo "xdebug.remote_enable=1" >> /usr/local/etc/php/php.ini

RUN mkdir /var/www/html/drupal

RUN ls -lhsa /var/www/html

#Uncomment the nexts lines if you need to import the backup.sql file 

#RUN chmod +x /var/www/html/drupal/docker-entrypoint.sh
#RUN chmod 755 /var/www/html/drupal/docker-entrypoint.sh

#ENTRYPOINT ["/var/www/html/drupal/docker-entrypoint.sh"]
#ENTRYPOINT ["docker-entrypoint.sh"]
