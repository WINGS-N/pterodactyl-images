# ---------------------------------------
# nginx with PHP 8.2 image by WINGS-N 
# ---------------------------------------
FROM     --platform=$TARGETOS/amd64 ghcr.io/wings-n/pterodactyl-images:os_debian_12

LABEL        author="WINGS-N" maintainer="nikita@wingshost.ru"

## install packages
RUN     apt update -y && apt -y install nginx

RUN     mkdir -p /root/nginx && ln -s /etc/nginx /root/nginx

ENV     HOME=/root

USER    root
WORKDIR	/root

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
