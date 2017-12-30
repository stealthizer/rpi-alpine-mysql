# rpi-alpine-mysql

Mysql/Mariadb Alpine Linux Docker image based on  https://github.com/Leafney/docker-alpine-mysql.
Current Mysql/MariaDB version: 10.1.26

#### parameter

* `MYSQL_ROOT_PWD` : root Password   default "mysql"
* `MYSQL_USER`     : new User
* `MYSQL_USER_PWD` : new User Password
* `MYSQL_USER_DB`  : new Database for new User

#### build image

```
$ docker build -t="stealthizer/rpi-alpine-mysql" .
```

#### run a default contaier

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 stealthizer/rpi-alpine-mysql:latest
```

#### run a container with new User and Password

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 -e MYSQL_ROOT_PWD=123 -e MYSQL_USER=dev -e MYSQL_USER_PWD=dev stealthizer/rpi-alpine-mysql:latest
```

#### run a container with new Database for new User and Password

```
$ docker run --name rpi-mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 -e MYSQL_ROOT_PWD=123 -e MYSQL_USER=dev -e MYSQL_USER_PWD=dev -e MYSQL_USER_DB=userdb stealthizer/rpi-alpine-mysql:latest
```
