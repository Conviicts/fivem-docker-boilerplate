FROM php:7-fpm

VOLUME /var/www

RUN docker-php-ext-install pdo pdo_mysql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin/ --filename=composer

RUN echo "date.timezone = 'Europe/Paris'" >> /usr/local/etc/php/conf.d/docker-php-weka-php.ini \
 && echo "memory_limit = '2G'" >> /usr/local/etc/php/conf.d/docker-php-weka-php.ini \
 && echo "log_errors = 'On'" >> /usr/local/etc/php/conf.d/docker-php-weka-php.ini \
 && echo "error_reporting = 'E_ALL'" >> /usr/local/etc/php/conf.d/docker-php-weka-php.ini \
 && echo "max_execution_time = '3600'" >> /usr/local/etc/php/conf.d/docker-php-weka-php.ini