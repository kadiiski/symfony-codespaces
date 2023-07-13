FROM debian:bullseye-slim
ARG DEBIAN_FRONTEND=noninteractive
USER root
COPY php.ini /tmp

RUN apt-get update -yq
    # Add updated php sources
RUN apt-get install curl -yq
RUN curl -sSL https://packages.sury.org/php/README.txt | bash -x
RUN apt-get update -yq
    # Install some common packages
RUN apt-get install git imagemagick nano openssh-server sqlite3 wget unzip -yq
RUN sed -i 's/<policy domain="coder" rights="none" pattern="PDF" \/>/<policy domain="coder" rights="read|write" pattern="PDF" \/>/g' /etc/ImageMagick-6/policy.xml
    # Install PHP CLI with some extensions for Drupal development
RUN apt-get install php8.2-dev -yq
RUN apt-get install php8.2-apcu php8.2-curl php8.2-gd php8.2-imagick php8.2-mbstring php8.2-sqlite3 php8.2-zip php8.2-intl -yq
RUN pear config-set php_ini /etc/php/8.2/cli/php.ini
RUN pecl install xdebug
RUN cat /tmp/php.ini >> /etc/php/8.2/cli/php.ini
    # Install NodeJS LTS
RUN curl -sL https://deb.nodesource.com/setup_lts.x | bash
RUN apt-get install nodejs -yq
    # Install Composer
RUN wget https://getcomposer.org/installer
RUN php installer --install-dir=/usr/local/bin --filename=composer
    # Install MySQL
RUN apt-get update && apt-get install -y mariadb-server php8.2-mysqli mariadb-client
    # Install Symfony Console
RUN wget https://get.symfony.com/cli/installer -O - | bash
RUN mv ~/.symfony5/bin/symfony /usr/local/bin/symfony
    # Clean up some things
RUN rm installer /tmp/php.ini
RUN rm -rf /var/lib/apt/lists/*
    # Create a user
#RUN useradd -m symfony -p symfony
#USER symfony
ENV SHELL /bin/bash
# start mariadb
RUN service mariadb start

