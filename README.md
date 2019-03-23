Docker + Alpine + MariaDB(Mysql)

This is an upgrade to the [leafney/docker-alpine-mysql](https://github.com/leafney/docker-alpine-mysql) project and renamed to `leafney/alpine-mariadb`.

#### Parameters

* `MYSQL_ROOT_PWD` : root Password default is "mysql"
* `MYSQL_USER`     : new UserName
* `MYSQL_USER_PWD` : new User Password
* `MYSQL_USER_DB`  : new Database for new User

#### Get Image from DockerHub

Download from DockerHub for `latest` tags or specific version tags:

```
$ docker pull leafney/alpine-mariadb:latest
```

#### Run a default contaier

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 leafney/alpine-mariadb:latest
```

#### Run a container with new User and Password

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 -e MYSQL_ROOT_PWD=123 -e MYSQL_USER=dev -e MYSQL_USER_PWD=dev leafney/alpine-mariadb:latest
```

#### Run a container with new Database for new User and Password

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 -e MYSQL_ROOT_PWD=123 -e MYSQL_USER=dev -e MYSQL_USER_PWD=dev -e MYSQL_USER_DB=userdb leafney/alpine-mariadb:latest
```
