FROM	debian:11

RUN apt update -y && apt upgrade -y && \
    #apt install -y nginx vim curl openssl && \
    apt install -y nginx openssl && \
    mkdir -p /etc/nginx/ssl /var/run/nginx && \
    openssl req -x509 -nodes -out /etc/nginx/ssl/inception.crt \
        -keyout /etc/nginx/ssl/inception.key \
        -subj "/C=ES/L=Malaga/O=42/OU=42/CN=gpaez-ga.42.fr/UID=gpaez-ga"

COPY	conf/nginx.conf /etc/nginx/nginx.conf

RUN	chmod 755 /var/www/html
RUN	chown -R www-data:www-data /var/www/html

CMD	["nginx", "-g", "daemon off;"]