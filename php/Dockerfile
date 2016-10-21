FROM php:7-apache
COPY php.ini /usr/local/etc/php/
RUN apt-get update \
  && apt-get install -y wget libpq-dev libfreetype6-dev libjpeg62-turbo-dev libpng12-dev libmcrypt-dev libbz2-dev \
  && docker-php-ext-install pdo_pgsql mbstring gd iconv mcrypt zip bz2 opcache
COPY virtual.conf /etc/apache2/sites-available/
RUN mkdir -p /var/log/httpd/php7.localdomain
RUN a2enmod rewrite && a2dissite 000-default && a2ensite virtual && service apache2 restart
RUN mkdir -p /var/www/adminer \
  && cd /var/www/adminer \
  && wget https://www.adminer.org/static/download/4.2.5/adminer-4.2.5.php \
  && wget https://raw.githubusercontent.com/vrana/adminer/master/designs/nicu/adminer.css \
  && mv adminer-4.2.5.php index.php
RUN curl -sS https://getcomposer.org/installer | php \
  && mv composer.phar /usr/local/bin/composer 
