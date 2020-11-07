FROM prowiki/mediawiki:35 as builder

WORKDIR /var/www/html/extensions

#RUN git clone https://github.com/wikimedia/mediawiki-extensions-Wikibase --depth=1 --branch=REL1_35 Wikibase

#RUN git clone https://github.com/wikimedia/mediawiki-extensions-UniversalLanguageSelector --depth=1 --branch=REL1_35 UniversalLanguageSelector
#RUN git clone https://github.com/wikimedia/mediawiki-extensions-cldr --depth=1 --branch=REL1_35 cldr

RUN git clone https://github.com/wikimedia/mediawiki-extensions-Elastica --depth=1 --branch=REL1_35 Elastica
RUN git clone https://github.com/wikimedia/mediawiki-extensions-CirrusSearch --depth=1 --branch=REL1_35 CirrusSearch
RUN git clone https://github.com/wikimedia/mediawiki-extensions-WikibaseCirrusSearch --depth=1 --branch=REL1_35 WikibaseCirrusSearch




FROM composer:1 as composer

COPY --from=builder /var/www/html /var/www/html
WORKDIR /var/www/html/
RUN composer install --no-dev -o
COPY composer.local.json /var/www/html/composer.local.json
RUN composer update --no-dev -o





FROM prowiki/mediawiki:35

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install --yes --no-install-recommends libbz2-dev=1.* gettext-base=0.19.* && \
    rm -rf /var/lib/apt/lists/*

RUN a2enmod rewrite

RUN install -d /var/log/mediawiki -o www-data

RUN docker-php-ext-install calendar bz2

COPY --from=composer /var/www/html /var/www/html
COPY htaccess /var/www/html/.htaccess

RUN ln -s /var/www/html/ /var/www/html/w

ENTRYPOINT ["/bin/bash"]
CMD ["apache2-foreground"]
