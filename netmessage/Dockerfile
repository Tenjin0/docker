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
    
RUN apt-get update && \
    apt-get install -y --force-yes \
    nginx \
    vim \
    curl
RUN rm /etc/nginx/nginx.conf
COPY ../netmessage_nginx/nginx.conf /etc/nginx/nginx.conf
RUN ln -s /etc/nginx/nginx.conf /etc/nginx/sites-available/
RUN ln -s /etc/nginx/nginx.conf /etc/nginx/sites-enabled/
RUN rm /etc/nginx/sites-enabled/default

RUN rm /etc/nginx/sites-available/default
EXPOSE 80
WORKDIR /etc/nginx
ADD start_script.sh .
RUN chmod 777 ./start_script.sh
CMD ./start_script.sh
