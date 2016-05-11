FROM php:5.6-apache
MAINTAINER Frederico Wuerges Becker <fred.wuerges@gmail.com>

# PHP.ini
COPY config/php.ini /usr/local/etc/php/

# PHP Extensions
RUN docker-php-ext-install mysql mysqli pdo pdo_mysql mbstring

# Install Composer
#RUN curl -sS https://getcomposer.org/installer | php \
#    && mv composer.phar /usr/local/bin/composer

# Configure apache
RUN chown -R www-data:www-data /var/www/html
RUN a2enmod rewrite headers deflate expire
RUN service apache2 restart

EXPOSE 8080

WORKDIR /var/www/html
