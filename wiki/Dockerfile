FROM mediawiki

RUN a2enmod ssl && a2enmod rewrite
RUN mkdir -p /etc/apache2/ssl

# COPY ../cert/. /etc/apache2/ssl
COPY 000-default.conf /etc/apache2/sites-available/000-default.conf
RUN sed -i '/SSLCertificateFile.*snakeoil\.pem/c\SSLCertificateFile \/etc\/apache2\/ssl\/inm-wiki.crt' /etc/apache2/sites-available/default-ssl.conf
RUN sed -i '/SSLCertificateKeyFile.*snakeoil\.key/c\SSLCertificateKeyFile \/etc\/apache2\/ssl\/inm-wiki.key' /etc/apache2/sites-available/default-ssl.conf
COPY rimera.png /var/www/html/resources/assets/rimera.png
COPY php.ini /usr/local/etc/php/php
# RUN ln -s /usr/local/etc/php/php.ini-production /usr/local/etc/php/php.ini

EXPOSE 80
EXPOSE 443