# 使用 MySQL 命令行界面体验最简单的 MySQL 操作

```sh
# 进入 MySQL 的 Docker 容器中并使用命令行工具连接 MySQL
$ sudo docker exec -it mysql mysql -uroot -p123456
mysql>

# 创建数据库
mysql> create database test;
Query OK, 1 row affected (0.02 sec)

# 选择数据库
mysql> use test;
Database changed

# 创建表
mysql> create table test_table(col1 varchar(10), col2 int);
Query OK, 0 rows affected (0.02 sec)

# 插入数据
mysql> insert into test_table(col1,col2) values('abc123', 1234);
Query OK, 1 row affected (0.01 sec)

# 查询数据
mysql> select * from test_table;
+--------+------+
| col1   | col2 |
+--------+------+
| abc123 | 1234 |
+--------+------+
1 row in set (0.00 sec)

# 更新数据
mysql> update test_table set col1='edf456', col2=5678 where col2=1234;
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0
mysql> select * from test_table;
+--------+------+
| col1   | col2 |
+--------+------+
| edf456 | 5678 |
+--------+------+
1 row in set (0.00 sec)

# 删除数据
mysql> delete from test_table where col2=5678;
Query OK, 1 row affected (0.01 sec)
mysql> select * from test_table;
Empty set (0.00 sec)
```
