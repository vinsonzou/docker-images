FROM alpine:3.4
MAINTAINER Vinson Zou <vinsoncou@gmail.com>

ENV TERM dumb   # See https://github.com/dockerfile/mariadb/issues/3

RUN mkdir /docker-entrypoint-initdb.d

RUN apk add --update mysql mysql-client bash pwgen && \
    rm -f /var/cache/apk/* && \
    mkdir -p /etc/mysql/conf.d \
    && { \
        echo '[mysqld]'; \
        echo 'skip-host-cache'; \
        echo 'skip-name-resolve'; \
        echo 'user = mysql'; \
        echo 'datadir = /var/lib/mysql'; \
        echo '!includedir /etc/mysql/conf.d/'; \
    } > /etc/mysql/my.cnf

VOLUME /var/lib/mysql

COPY docker-entrypoint.sh /usr/local/bin/
RUN chmod a+x /usr/local/bin/docker-entrypoint.sh
ENTRYPOINT ["docker-entrypoint.sh"]

EXPOSE 3306
CMD ["mysqld"]
