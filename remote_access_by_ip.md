[20190508]

#### 远程连接

原来的IP地址，
在文件：
`/etc/mysql/mysql.conf.d`

```bash
[mysqld]
bind-address = 127.0.0.1
```

地址修改为：

`0.0.0.0`，需要**重启mysql服务**。

```bash
$ sudo systemctl stop mysql
$ sudo systemctl start mysql
```

### 参考

https://serverfault.com/questions/895826/connecting-to-a-remote-mysql-database-using-its-private-ip-address
