FROM php:7.0-fpm
RUN curl -o /usr/local/bin/composer https://getcomposer.org/download/1.8.4/composer.phar && \
    chmod +x /usr/local/bin/composer && \
    echo deb http://mirrors.aliyun.com/debian stretch main contrib non-free > /etc/apt/sources.list && \
    echo deb http://mirrors.aliyun.com/debian stretch-proposed-updates main contrib non-free >> /etc/apt/sources.list && \
    echo deb http://mirrors.aliyun.com/debian stretch-updates main contrib non-free >> /etc/apt/sources.list && \
    echo deb-src http://mirrors.aliyun.com/debian stretch main contrib non-free >> /etc/apt/sources.list && \
    echo deb-src http://mirrors.aliyun.com/debian stretch-proposed-updates main contrib non-free >> /etc/apt/sources.list && \
    echo deb-src http://mirrors.aliyun.com/debian stretch-updates main contrib non-free >> /etc/apt/sources.list && \
    echo deb http://mirrors.aliyun.com/debian-security/ stretch/updates main non-free contrib >> /etc/apt/sources.list && \
    echo deb-src http://mirrors.aliyun.com/debian-security/ stretch/updates main non-free contrib >> /etc/apt/sources.list && \
    echo deb http://mirrors.aliyuncs.com/debian stretch main contrib non-free >> /etc/apt/sources.list && \
    echo deb http://mirrors.aliyuncs.com/debian stretch-proposed-updates main contrib non-free >> /etc/apt/sources.list && \
    echo deb http://mirrors.aliyuncs.com/debian stretch-updates main contrib non-free >> /etc/apt/sources.list && \
    echo deb-src http://mirrors.aliyuncs.com/debian stretch main contrib non-free >> /etc/apt/sources.list && \
    echo deb-src http://mirrors.aliyuncs.com/debian stretch-proposed-updates main contrib non-free >> /etc/apt/sources.list && \
    echo deb-src http://mirrors.aliyuncs.com/debian stretch-updates main contrib non-free >> /etc/apt/sources.list && \
    echo deb http://mirrors.aliyuncs.com/debian-security/ stretch/updates main non-free contrib >> /etc/apt/sources.list && \
    echo deb-src http://mirrors.aliyuncs.com/debian-security/ stretch/updates main non-free contrib >> /etc/apt/sources.list && \
    apt-get update && \
    apt-get install -y zlib1g-dev && \
    docker-php-ext-install pdo_mysql && \
    docker-php-ext-install zip && \
    pecl install mongodb.tgz && \
    echo extension=mongodb.so > /usr/local/etc/php/conf.d/mongodb.ini && \
    cp /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini