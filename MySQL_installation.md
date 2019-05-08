[20190508]

### 安装过程

#### Step 1: Install MySQL

```bash
$ sudo apt-get update
$ sudo apt-get install mysql-server
```
中间会提醒我们创建`root`密码。

passwd: ******

#### Step 2: 配置MySQL

```bash
$ mysql_secure_installation
```

#### Step 3: 测试MySQL

```bash
$ systemctl status mysql.service
```

输出:

```bash
● mysql.service - MySQL Community Server
   Loaded: loaded (/lib/systemd/system/mysql.service; enabled; vendor preset: enabled)
   Active: active (running) since 三 2019-05-08 14:17:50 CST; 5min ago
 Main PID: 26529 (mysqld)
   CGroup: /system.slice/mysql.service
           └─26529 /usr/sbin/mysqld
```

如果不是上面的结果：
```bash
sudo systemctl start mysql
```

额外的测试：连接数据库。

```bash
$ mysqladmin -p -u root version
```

输出：

```bash
Enter password:
mysqladmin  Ver 8.42 Distrib 5.7.26, for Linux on x86_64
Copyright (c) 2000, 2019, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Server version		5.7.26-0ubuntu0.16.04.1
Protocol version	10
Connection		Localhost via UNIX socket
UNIX socket		/var/run/mysqld/mysqld.sock
Uptime:			5 min 57 sec

Threads: 1  Questions: 12  Slow queries: 0  Opens: 115  Flush tables: 1  Open tables: 34  Queries per second avg: 0.033
```


### 参考

https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-16-04
