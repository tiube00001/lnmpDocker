FROM php:7.0-fpm
ADD ./composer.phar /usr/local/bin/composer
ADD ./mongodb-1.5.3.tgz /usr/share/mongodb-1.5.3.tgz
RUN chmod +x /usr/local/bin/composer && \
    echo deb http://mirrors.aliyun.com/debian stretch main contrib non-free > /etc/apt/sources.list && \
    echo deb http://mirrors.aliyun.com/debian stretch-proposed-updates main contrib non-free >> /etc/apt/sources.list && \
    echo deb http://mirrors.aliyun.com/debian stretch-updates main contrib non-free >> /etc/apt/sources.list && \
    echo deb-src http://mirrors.aliyun.com/debian stretch main contrib non-free >> /etc/apt/sources.list && \
    echo deb-src http://mirrors.aliyun.com/debian stretch-proposed-updates main contrib non-free >> /etc/apt/sources.list && \
    echo deb-src http://mirrors.aliyun.com/debian stretch-updates main contrib non-free >> /etc/apt/sources.list && \
    echo deb http://mirrors.aliyun.com/debian-security/ stretch/updates main non-free contrib >> /etc/apt/sources.list && \
    echo deb-src http://mirrors.aliyun.com/debian-security/ stretch/updates main non-free contrib >> /etc/apt/sources.list && \
    rm -rf /etc/apt/sources.list.d/* && \
    apt install libpng-dev -y && \
    apt-get update && \
    apt-get install -y zlib1g-dev && \
    docker-php-ext-install pdo_mysql && \
    docker-php-ext-install zip && \
    docker-php-ext-install bcmath && \
    docker-php-ext-install gd && \
    cd /usr/share && \
    pecl install mongodb-1.5.3.tgz && \
    echo extension=mongodb.so > /usr/local/etc/php/conf.d/mongodb.ini && \
    cd / && \
    cp /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini && \
    mkdir -p /usr/share/composer/cache