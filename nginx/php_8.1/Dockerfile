# ---------------------------------------
# PHP 8.2 image by WINGS-N 
# ---------------------------------------
FROM    ghcr.io/wings-n/pterodactyl-images:php_8.1

LABEL    author="WINGS-N" maintainer="nikita@wingshost.ru"

## install packages
RUN     dpkg --add-architecture i386

RUN     apt update && apt install nginx

ENV     HOME=/home/container

USER    container
WORKDIR	/home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
