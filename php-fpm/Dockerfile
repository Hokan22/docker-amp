FROM php:7.2-fpm

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        libmemcached-dev \
        libz-dev \
        libzip-dev \
        libpq-dev \
        libjpeg-dev \
        libpng-dev \
        libfreetype6-dev \
        libssl-dev \
        libmcrypt-dev \
        openssh-server \
        git \
        wget \
        unzip \
        cron \
        nano \
        zsh

# Download Grml ZSH Config
RUN wget -qO /root/.zshrc https://git.grml.org/f/grml-etc-core/etc/zsh/zshrc

# Install the PHP pcntl extention
RUN docker-php-ext-install pcntl
# Install the PHP zip extention
RUN docker-php-ext-install zip
# Install the PHP pdo_mysql extention
RUN docker-php-ext-install pdo_mysql
# Install the PHP mysqli extention
RUN docker-php-ext-install mysqli
# Install the PHP json extention
RUN docker-php-ext-install json
# Install the PHP mongodb extention
RUN pecl install mongodb
RUN docker-php-ext-enable mongodb

# Install the PHP gd library
RUN docker-php-ext-install gd && \
    docker-php-ext-configure gd \
        --enable-gd-native-ttf \
        --with-jpeg-dir=/usr/lib \
        --with-freetype-dir=/usr/include/freetype2 && \
    docker-php-ext-install gd



COPY composer.sh  /var/www/html/composer.sh
RUN ./composer.sh