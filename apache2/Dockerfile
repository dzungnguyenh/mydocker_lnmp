FROM webdevops/apache:ubuntu-16.04

MAINTAINER Dzung Nguyen <dung.nguyen@asiantech.vn>

ARG PHP_SOCKET="php-fpm:9000"

ENV WEB_PHP_SOCKET=$PHP_SOCKET

ENV WEB_DOCUMENT_ROOT=/var/www/html

EXPOSE 80 443

WORKDIR /var/www/html

ENTRYPOINT ["/opt/docker/bin/entrypoint.sh"]

CMD ["supervisord"]
