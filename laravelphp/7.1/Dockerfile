FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive
ENV TZ="Europe/Andorra"

RUN apt-get update \
    && apt-get install -y curl zip unzip git software-properties-common \
    && add-apt-repository -y ppa:ondrej/php \
    && apt-get update \
    && apt-get install -y php7.1-cli php7.1-mcrypt php7.1-gd php7.1-mysql php7.1-bcmath php7.1-zip \
       php7.1-pgsql php7.1-imap php-memcached php7.1-mbstring php7.1-xml php7.1-curl php7.1-imagick\
    && update-alternatives --set php /usr/bin/php7.1 \
    && php -r "readfile('https://getcomposer.org/installer');" | php -- --install-dir=/usr/bin --filename=composer --1 \
    && apt-get remove -y --purge software-properties-common \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

WORKDIR /opt

CMD ["php", "-a"]
