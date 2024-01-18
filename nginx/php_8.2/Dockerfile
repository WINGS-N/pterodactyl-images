# ---------------------------------------
# nginx with PHP 8.2 image by WINGS-N 
# ---------------------------------------
FROM     ghcr.io/wings-n/pterodactyl-images:php_8.2

LABEL    author="WINGS-N" maintainer="nikita@wingshost.ru"

USER    root
## install packages
RUN     dpkg --add-architecture amd64

RUN     apt update -y && apt -y install nginx

RUN     mkdir -p /home/container/nginx && ln -s /etc/nginx /home/container/nginx

ENV     HOME=/home/container

USER    container
WORKDIR	/home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
