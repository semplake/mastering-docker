FROM alpine:latest
LABEL maintainer="camprette<ajibaskoro@bajau.com>"
LABEL description="dockerfile example for php and apache"

ENV 	PHPVER=7 APACHEVER=2 MYSQLVER=7.2.8-r1

RUN 	apk add --update apache${APACHEVER} php${PHPVER}-apache${APACHEVER} php${PHPVER} php${PHPVER}-mysqli-${MYSQLVER} && \
	rm -rf /var/cache/apk/* && \
	mkdir /run/apache${APACHEVER}/ && \
	rm -rf /var/www/localhost/htdocs/index.html && \
	echo "<?php phpinfo(); ?>" > /var/www/localhost/htdocs/index.php && \
	chmod 755 /var/www/localhost/htdocs/index.php


EXPOSE 80/tcp

ENTRYPOINT ["httpd"]
CMD ["-D", "FOREGROUND"]
