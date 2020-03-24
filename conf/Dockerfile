FROM seniocaires/php_7_oracle_12

ADD sites-enabled /etc/apache2/sites-enabled
COPY php.ini /etc/php/7.0/apache2

RUN apt update
RUN DEBIAN_FRONTEND=noninteractive apt --assume-yes --no-upgrade install -y php7.0-gd
RUN DEBIAN_FRONTEND=noninteractive apt --assume-yes --no-upgrade install -y vim
RUN DEBIAN_FRONTEND=noninteractive apt --assume-yes --no-upgrade install -y git

ADD sites-enabled /etc/apache2/sites-enabled
COPY php.ini /etc/php/7.2/apache2
COPY composer.phar /usr/local/bin/composer

RUN chmod 777 /usr/local/bin/composer
RUN composer self-update

ENTRYPOINT ["/bin/bash", "-c", "a2enmod rewrite && service apache2 restart && tail -f /dev/null"]
