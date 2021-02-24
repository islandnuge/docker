FROM phpdockerio/php80-fpm:latest
WORKDIR "/application"

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y --no-install-recommends apt-utils

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install php-memcached php8.0-mysql php8.0-pgsql php-redis php8.0-sqlite3 php-xdebug php8.0-bcmath php8.0-dba php8.0-gmp php-imagick php8.0-intl php-msgpack php8.0-odbc php8.0-snmp php8.0-soap php8.0-tidy php7.4-xmlrpc php-yaml \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# Install composer
RUN cd /tmp && \
    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php composer-setup.php --install-dir=/usr/bin --filename=composer

# Install nodejs & npm
RUN curl -sL https://deb.nodesource.com/setup_15.x -o nodesource_setup.sh && \
	chmod +x nodesource_setup.sh && \
	./nodesource_setup.sh && \
	apt-get -y install nodejs && \
	apt-get -y install build-essential && \
	rm ./nodesource_setup.sh

RUN apt-get update; apt-get install iputils-ping -y

ENV DEBIAN_FRONTEND teletype
