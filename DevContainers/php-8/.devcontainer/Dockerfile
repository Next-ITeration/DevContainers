#######################################################################################
##     The Base image with usable tools
#######################################################################################

FROM registry.access.redhat.com/ubi8/ubi-minimal:latest AS osbase

LABEL maintainer="Alejandro Medici <alejandro.medici@bnextiteration.com.ar>" \
      name="nit-php8-dev-container" \
      author="NiT Team" \
      vendor="NiT" \
      release="0.1.0" \
      summary="NiT Dev Environment containers" \
      description="Defined the proper setup to be used with Visual Studio Code for PHP7.4"

RUN microdnf update && \
    microdnf -y install wget tar gzip git && \
    microdnf clean all && rm -rf /var/cache/microdnf

#installing PHP
RUN microdnf upgrade
RUN microdnf module reset php
RUN microdnf module enable php:8.0
RUN microdnf install php
RUN microdnf -y install php php-{cli,fpm,mysqlnd,zip,devel,gd,mbstring,curl,xml,pear,bcmath,json}

# Adding composer as actually is one of the most used package manager for PHP
#RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
#RUN php -r "if (hash_file('sha384', 'composer-setup.php') === '55ce33d7678c5a611085589f1f3ddf8b3c52d662cd01d4ba75c0ee0459970c2200a51f492d557530c71c15d8dba01eae') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
#RUN php composer-setup.php
#RUN php -r "unlink('composer-setup.php');"
#RUN mv composer.phar /usr/local/bin/composer

COPY --from=composer/composer:latest-bin /composer /usr/local/bin/composer

COPY ./ /scripts

WORKDIR /scripts

CMD ["/bin/bash"]