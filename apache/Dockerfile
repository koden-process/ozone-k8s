FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    software-properties-common \
    curl \
    wget \
    vim \
    unzip \
    git

RUN add-apt-repository ppa:ondrej/php \
    && apt-get update

RUN apt-get install -y libapache2-mod-php5.6

RUN apt-get install -y \
    php5.6 \
    php5.6-cli \
    php5.6-fpm \
    php5.6-mysql \
    php5.6-curl \
    php5.6-json \
    php5.6-cgi \
    php5.6-xml \
    php5.6-mbstring \
    php5.6-zip \
    php5.6-gd

COPY php.ini /etc/php/5.6/apache2/php.ini

RUN apt-get install -y apache2 && apt-get clean

RUN a2enmod php5.6
RUN a2enmod rewrite

RUN apt-get install -y pdftk

EXPOSE 80

CMD ["apachectl", "-D", "FOREGROUND"]