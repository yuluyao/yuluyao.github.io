---
layout: post
category: linux
---

## install

安装
```shell
yum install https://download.postgresql.org/pub/repos/yum/reporpms/EL-7-x86_64/pgdg-redhat-repo-latest.noarch.rpm

yum install postgresql10

yum install postgresql10-server
```

开启服务
```shell
/usr/pgsql-10/bin/postgresql-10-setup initdb
systemctl enable postgresql-10
systemctl start postgresql-10
```


环境变量

在linux的postgres用户的主文件夹中，设置环境变量。主文件夹可以在`/etc/passwd`中查询，一般是`/var/lib/pgsql`。

在`.bash_profile`中加入以下内容。

```shell
PGDATA=/var/lib/pgsql/10/data
export PGDATA
PGHOME=/usr/pgsql-10/
export PGHOME
```

[postgresql官网教程](https://www.postgresql.org/download/linux/redhat/)