FROM alpine:latest
MAINTAINER ltxlong

# install nginx
RUN apk --update add nginx && rm -rf /var/cache/apk/*

# Change Webroot Permissions
RUN mkdir /var/www/html/

RUN mkdir -p /run/nginx

# ensure www-data user exists
RUN set -x \
    && adduser -u 82 -D -S -G www-data www-data

RUN chown -R www-data:www-data /var/www/html/ /var/log/nginx/

EXPOSE 80 443

CMD ["nginx","-g","daemon off;"]
