# ---------------------------------------
# PHP 8.2 image by WINGS-N 
# ---------------------------------------
FROM    ghcr.io/parkervcp/yolks:debian

LABEL    author="WINGS-N" maintainer="nikita@wingshost.ru"

## install packages
RUN     dpkg --add-architecture i386 \
        && apt update -y \
        && apt install -y --no-install-recommends gnupg2 tzdata \
        software-properties-common ca-certificates apt-transport-https gnupg2

RUN     echo "deb https://packages.sury.org/php/ buster main" >> /etc/apt/sources.list \
        && wget -qO - https://packages.sury.org/php/apt.gpg | apt-key add -

RUN     apt update -y \
        && apt install -y php8.1 php8.1-common php8.1-cli php8.1-gd \
        php8.1-mysql php8.1-mbstring php8.1-bcmath php8.1-xml php8.1-fpm \
        php8.1-curl php8.1-zip php8.1-readline php8.1-yaml \
	php8.1-tokenizer php8.1-dom php8.1-cgi libphp8.1-embed

ENV     HOME=/home/container PHP_INI_SCAN_DIR=/home/container

USER    container
WORKDIR	/home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
