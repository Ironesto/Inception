FROM	debian:11

RUN	apt update -y && apt upgrade -y && \
	apt install -y php7.4 php-fpm php-mysql mariadb-client curl && \
	mkdir -p /var/www/html && \
	adduser -D -H -S -G www-data www-data && \
	chown -R www-data:www-data /var/www/html && \
	cd /var/www/html && \
	curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar && \
	chmod +x wp-cli.phar && \
	mv wp-cli.phar /usr/local/bin/wp

COPY	conf/www.conf /etc/php/7.4/fpm/pool.d
COPY	tools/auto_config.sh /auto_config.sh
RUN	chmod +x auto_config.sh

CMD	["/auto_config.sh"]