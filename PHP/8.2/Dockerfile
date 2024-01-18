# ---------------------------------------
# PHP 8.2 image by WINGS-N 
# ---------------------------------------
FROM     --platform=$TARGETOS/amd64 ghcr.io/wings-n/os_debian_12

LABEL    author="WINGS-N" maintainer="nikita@wingshost.ru"

## install packages
RUN     dpkg --add-architecture amd64 \
        && apt update -y \
        && apt install -y --no-install-recommends gnupg2 tzdata \
        software-properties-common ca-certificates apt-transport-https gnupg2 wget libc6
        
RUN     wget http://mirrors.edge.kernel.org/debian/pool/main/libf/libffi/libffi6_3.2.1-9_amd64.deb && dpkg -i libffi6_3.2.1-9_amd64.deb

RUN     echo "deb https://packages.sury.org/php/ buster main" >> /etc/apt/sources.list \
        && wget -qO - https://packages.sury.org/php/apt.gpg | apt-key add -

RUN     apt update -y \
        && apt install -y php8.2 php8.2-common php8.2-cli php8.2-gd \
        php8.2-mysql php8.2-mbstring php8.2-bcmath php8.2-xml php8.2-fpm \
        php8.2-curl php8.2-zip php8.2-readline php8.2-yaml \
	php8.2-tokenizer php8.2-dom php8.2-cgi libphp8.2-embed

ENV     HOME=/root/ PHP_INI_SCAN_DIR=/root/

USER    root
WORKDIR	/root

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
