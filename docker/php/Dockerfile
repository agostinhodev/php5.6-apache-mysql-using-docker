# Use the official Ubuntu 20.04 base image
FROM ubuntu:20.04

# Install necessary packages for the application
RUN apt-get update -y && apt-get install -y software-properties-common \
    ca-certificates \
    lsb-release \
    apt-transport-https \
    libpng-dev \
    libfreetype6-dev \
    curl \
    gnupg2 \
    supervisor

# Install php5.6
RUN LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php && apt-get update -y && apt-get install -y php5.6

# Install php5.60 extensions
RUN apt-get install -y dialog \
    git \
    gnupg \
    php5.6-fpm \
    php5.6-iconv \
    php5.6-pdo-mysql \
    php5.6-curl \
    php5.6-mbstring \
    php5.6-bcmath \
    php5.6-xml \
    php5.6-soap \
    php5.6-intl \
    php5.6-sockets \
    php5.6-zip \
    php5.6-gd \
    php5.6-mcrypt \
    php5.6-sqlite3 \
    gettext-base \
    python3 \
    python3-pip \
    php5.6-cli \
    php5.6-common \
    php5.6-json \
    php5.6-mysql

# Install apache
RUN apt-get install -y apache2

# Enable necessary Apache modules
RUN a2enmod proxy_fcgi setenvif
RUN a2enconf php5.6-fpm

# Configure timezone
ENV DEBIAN_FRONTEND noninteractive
ENV TZ=America/Sao_Paulo
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Add a custom php.ini file (optional)
COPY php.ini /etc/php/5.6/apache2/conf.d/40-custom.ini

# Create a directory for PHP-FPM socket
RUN mkdir /run/php

# Copy the supervisor configuration file for keeping services running
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

# Expose Apache port
EXPOSE 80

# Start supervisor to keep Apache and PHP-FPM running
CMD ["/usr/bin/supervisord", "-n", "-c", "/etc/supervisor/conf.d/supervisord.conf"]
