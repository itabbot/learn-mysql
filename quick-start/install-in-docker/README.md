# 使用 Docker 安装 MySQL

1. 拉取 MySQL 的最新版 Docker 镜像（[其他版本>>](https://hub.docker.com/_/mysql/tags)）

```sh
$ sudo docker pull mysql

Using default tag: latest
latest: Pulling from library/mysql
bc377bce3181: Pull complete 
80bab949ab51: Pull complete 
73682200afb7: Pull complete 
d1c32d486523: Pull complete 
54341582c90c: Pull complete 
7490cd8f4d9b: Pull complete 
de967683cb3b: Pull complete 
39564f901a1e: Pull complete 
c95e6efa291a: Pull complete 
8366d05afd7c: Pull complete 
Digest: sha256:85ab57eb4a48ada2a341dcf7d96733ce2f370fffb8e8e216991b106e50fa6434
Status: Downloaded newer image for mysql:latest
docker.io/library/mysql:latest
```

2. 将镜像作为容器运行

```sh
$ sudo docker run --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123456 -d mysql
1789921f5f38559bdd2198e3e6e80b20cb9d2b7457e54285859b3e2368582b0e
```

3. 检查容器是否正在运行

```sh
$ sudo docker container ls

CONTAINER ID   IMAGE     COMMAND                   CREATED          STATUS          PORTS                                                  NAMES
1789921f5f38   mysql     "docker-entrypoint.s…"   29 seconds ago   Up 28 seconds   0.0.0.0:3306->3306/tcp, :::3306->3306/tcp, 33060/tcp   mysql
```

4. 进入容器中并使用命令行工具连接 MySQL

```sh
$ sudo docker exec -it mysql mysql -uroot -p123456

mysql: [Warning] Using a password on the command line interface can be insecure.
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 10
Server version: 8.1.0 MySQL Community Server - GPL

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> 
```
