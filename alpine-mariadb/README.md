# mariadb

This is docker image to run a MariaDB database server.

[![](https://images.microbadger.com/badges/image/vinsonzou/alpine-mariadb.svg)](http://microbadger.com/images/vinsonzou/alpine-mariadb "Get your own image badge on microbadger.com")

From image: alpine:3.7

MariaDB Server: 10.1.28

## FREE ACCESS to server! Why?

You are using image docker inside your infrastructure of docker. Take care to protect its!

## NO SQL DUMPS! SAVE TIME!
Connect your DB thouth volume.

```
-v /my/database:/var/lib/mysql
```

## You start with a clean slate?
Mount empty folder into volume.

## INCLUDE YOUR CONFIG
This is a simple 

```
-v /my/custom/configs:/etc/mysql/conf.d
```

## QUICK START
```
$ docker run --rm -e "MYSQL_ROOT_PASSWORD=test" -v /my/empty/database:/var/lib/mysql -p 3306:3306 vinsonzou/alpine-mariadb
```

## TRY NOW
Make container with mysql server

```
$ mkdir -p /tmp/empty/db

$ docker run --rm --name "mysqlsrv" -v /tmp/empty/db:/var/lib/mysql vinsonzou/alpine-mariadb

```
Ok. Make empty folder for data and server up.

Now, Use `docker exec` into the container. (Docker version >= 1.3)

```
$ docker exec -it mysqlsrv sh
```

Ok. You into container.

```
# mysql -uroot -p
```
Woooow!

```
MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
+--------------------+
3 rows in set (0.00 sec)
```

Now you see in folder /tmp/empty/db

### Thanks for reading!
