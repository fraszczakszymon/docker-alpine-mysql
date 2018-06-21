Docker + Alpine-3.7 + Mysql/MariaDB-10.1.18

#### Parameters

* `MYSQL_ROOT_PWD` : root password, default "mysql"
* `MYSQL_USER`     : new user
* `MYSQL_USER_PWD` : new user password
* `MYSQL_USER_DB`  : new database for new user

#### Build image

```
$ docker build -t fraszczakszymon/mysql-alpine .
```

#### Run a default container

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 fraszczakszymon/mysql-alpine
```

#### Run a container with new user and password

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 -e MYSQL_ROOT_PWD=123 -e MYSQL_USER=dev -e MYSQL_USER_PWD=dev fraszczakszymon/mysql-alpine
```

#### Run a container with new database for new user and password

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 -e MYSQL_ROOT_PWD=123 -e MYSQL_USER=dev -e MYSQL_USER_PWD=dev -e MYSQL_USER_DB=userdb fraszczakszymon/mysql-alpine
```
