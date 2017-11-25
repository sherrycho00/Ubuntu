[修改MySQL root 账号的密码](https://segmentfault.com/a/1190000002498643)

### 修改MySQL root账号密码出现“auth_socket"

首先查看user表
```
mysql> select user, plugin from mysql.user;
+------------------+-----------------------+
| user             | plugin                |
+------------------+-----------------------+
| root             | auth_socket           |
| mysql.session    | mysql_native_password |
| mysql.sys        | mysql_native_password |
| debian-sys-maint | mysql_native_password |
| sherry           | mysql_native_password |
| jay              | mysql_native_password |
+------------------+-----------------------+
6 rows in set (0.00 sec)
```

可以看到root的plugin被修改成了auth_socket，只需将其修改回mysql_native_password即可
```
mysql> update mysql.user set authentication_string=PASSWORD('111111'), 
    -> plugin='mysql_native_password' where user='root';
```
```
mysql> flush privileges;
```

[mysql 普通用户无权限连接问题](http://www.jianshu.com/p/2b63c65caf6a)


