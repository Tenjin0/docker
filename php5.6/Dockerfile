FROM ubuntu:15.04
RUN apt-get update && \
 apt-get install -y software-properties-common
RUN add-apt-repository ppa:ondrej/php5-5.6 -y

RUN apt-get install -y --force-yes \
    php5 \
    php5-fpm \
    php5-cli \
    php5-mysql \
    php5-mcrypt \
    php5-common \
    php5-dev \
    php5-curl \
    php5-gd \
    php5-intl \
    mysql-client \
    php-pear
RUN pecl install xdebug
CMD /bin/bash
