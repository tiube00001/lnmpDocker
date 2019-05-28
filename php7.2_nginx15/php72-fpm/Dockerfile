FROM php:7.2.1-fpm
ADD ./composer.phar /usr/local/bin/composer
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
    apt-get update && \
    apt-get install -y zlib1g-dev && \
    docker-php-ext-install pdo_mysql && \
    docker-php-ext-install zip && \
    mkdir -p /usr/share/composer/cache