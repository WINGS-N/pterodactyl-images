# ---------------------------------------
# nginx with PHP 8.2 image by WINGS-N 
# ---------------------------------------
FROM     ghcr.io/wings-n/pterodactyl-images:php_8.2

LABEL    author="WINGS-N" maintainer="nikita@wingshost.ru"

## install packages
RUN     dpkg --add-architecture amd64

RUN     sudo apt update -y && sudo apt -y install nginx

ENV     HOME=/home/container

USER    container
WORKDIR	/home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
