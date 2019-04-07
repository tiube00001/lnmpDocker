FROM php:7.0-fpm
ADD https://github.com/swoole/swoole-src/archive/master.tar.gz /build/swoole.tar.gz
RUN echo "deb http://mirrors.cloud.aliyuncs.com/debian stable main contrib non-free" > /etc/apt/sources.list && \
    echo "deb http://mirrors.cloud.aliyuncs.com/debian stable-proposed-updates main contrib non-free" >> /etc/apt/sources.list && \
    echo "deb http://mirrors.cloud.aliyuncs.com/debian stable-updates main contrib non-free" >> /etc/apt/sources.list && \
    echo "deb-src http://mirrors.cloud.aliyuncs.com/debian stable main contrib non-free" >> /etc/apt/sources.list && \
    echo "deb-src http://mirrors.cloud.aliyuncs.com/debian stable-proposed-updates main contrib non-free" >> /etc/apt/sources.list && \
    echo "deb-src http://mirrors.cloud.aliyuncs.com/debian stable-updates main contrib non-free" >> /etc/apt/sources.list && \
    echo "deb http://mirrors.aliyun.com/debian stable main contrib non-free" >> /etc/apt/sources.list && \
    echo "deb http://mirrors.aliyun.com/debian stable-proposed-updates main contrib non-free" >> /etc/apt/sources.list && \
    echo "deb http://mirrors.aliyun.com/debian stable-updates main contrib non-free" >> /etc/apt/sources.list && \
    echo "deb-src http://mirrors.aliyun.com/debian stable main contrib non-free" >> /etc/apt/sources.list && \
    echo "deb-src http://mirrors.aliyun.com/debian stable-proposed-updates main contrib non-free" >> /etc/apt/sources.list && \
    echo "deb-src http://mirrors.aliyun.com/debian stable-updates main contrib non-free" >> /etc/apt/sources.list && \
    apt-get update && \
    apt-get install -y libssl-dev && \
    apt-get install -y libnghttp2-dev && \
    apt-get install -y libhiredis-dev && \
    docker-php-ext-install sockets && \
    docker-php-ext-install pdo_mysql && \
    cd /build && \
    rm -rf ./swoole-src && \
    tar zxvf ./swoole.tar.gz && \
    mv swoole-src* swoole-src && \
    cd swoole-src && \
    phpize && \
    ./configure \
        --enable-openssl  \
        --enable-http2  \
        --enable-async-redis \
        --enable-mysqlnd  \
        --enable-sockets  && \
    make clean && make && make install && \
    echo extension=swoole.so > /usr/local/etc/php/conf.d/swoole.ini && \
    rm -rf /build