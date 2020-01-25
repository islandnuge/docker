FROM phpdockerio/php74-fpm:latest
WORKDIR "/application"

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y --no-install-recommends apt-utils

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install php-memcached php7.4-mysql php7.4-pgsql php-redis php7.4-sqlite3 php-xdebug php7.4-bcmath php7.4-dba php7.4-gmp php-imagick php7.4-intl php-msgpack php7.4-odbc php7.4-snmp php7.4-soap php7.4-tidy php7.4-xmlrpc php-yaml \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# Install composer
RUN cd /tmp && \
    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php composer-setup.php --install-dir=/usr/bin --filename=composer

# Install nodejs & npm
RUN curl -sL https://deb.nodesource.com/setup_13.x -o nodesource_setup.sh && \
	chmod +x nodesource_setup.sh && \
	./nodesource_setup.sh && \
	apt-get -y install nodejs && \
	apt-get -y install build-essential && \
	rm ./nodesource_setup.sh

RUN apt-get update; apt-get install iputils-ping -y