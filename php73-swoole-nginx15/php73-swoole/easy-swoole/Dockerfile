FROM swoole:4.1.3
COPY composer.phar /usr/local/bin/composer
COPY mongodb-1.5.3.tgz /build/mongodb-1.5.3.tgz
ENV COMPOSER_HOEM /user/share/composer
ENV COMPOSER_CACHE_DIR /user/share/composer/cache
WORKDIR /app
RUN chmod +x /usr/local/bin/composer && \
    apt-get update && \
    apt-get install -y zlib1g-dev && \
    docker-php-ext-install zip && \
    pecl install -O /build/mongodb-1.5.3.tgz && \
    echo extension=mongodb.so > /usr/local/etc/php/conf.d/mongodb.ini && \
    cd /app && \
    composer config -g repo.packagist composer https://packagist.phpcomposer.com && \
    composer require easyswoole/easyswoole -vvv && \
    php vendor/bin/easyswoole install && \
    composer clear-cache
EXPOSE 9501
ENTRYPOINT ["php", "/app/easyswoole", "start"]