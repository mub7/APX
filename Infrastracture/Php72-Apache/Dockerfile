#############################################################
# Docker File PHP72-Apache

# Create Apache Webserver Environment with PHP 7.2 & XDebug Extension Version 2.8.0
#
#
#
# Mustafa, 2020
#
#############################################################
FROM php:7.2-apache
RUN docker-php-ext-install mysqli
RUN pecl install xdebug-2.8.0
RUN docker-php-ext-enable xdebug
RUN echo "xdebug.remote_enable=1" >> /usr/local/etc/php/php.ini
