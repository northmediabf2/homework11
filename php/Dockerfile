#Используем образ из Docker Hub
FROM php:7.4-fpm  
#Ставим пакеты                                     
RUN apt-get update && apt-get install -y \             
        libfreetype6-dev \
        wget \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd \
    && apt-get clean -y

#ADD ./php.ini /usr/local/etc/php/php.ini
#ADD configs/www.conf /usr/local/etc/php-fpm.d/
RUN wget https://getcomposer.org/installer -O - -q \
    | php -- --install-dir=/bin --filename=composer --quiet

RUN groupadd -g 1000 www
RUN useradd -u 1000 -ms /bin/bash -g www www

WORKDIR /var/www

USER "${USER_ID}:${GROUP_ID}"

CMD ["php-fpm"]
