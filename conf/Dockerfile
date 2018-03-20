FROM seniocaires/php_7_oracle_12

ADD sites-enabled /etc/apache2/sites-enabled
COPY php.ini /etc/php/7.0/apache2

RUN apt update
RUN apt install -y php7.0-gd
