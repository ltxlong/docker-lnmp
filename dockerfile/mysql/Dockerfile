FROM alpine:latest
MAINTAINER ltxlong

COPY ./docker-entrypoint.sh /

RUN chmod +x /docker-entrypoint.sh \
    && addgroup -S mysql \
    && adduser -S mysql -G mysql \
    && apk --update add mysql mysql-client \
    && rm -rf /var/cache/apk/*

COPY ./my.cnf /etc/mysql/my.cnf

EXPOSE 3306

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["mysqld", "--user=mysql"]