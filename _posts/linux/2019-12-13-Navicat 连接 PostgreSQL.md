---
layout: post
category: linux
---

PostgreSQL默认不可以远程连接，要修改默认配置以后才可以远程连接。

1. 修改`${PGDATA}/pg_hba.conf`

增加一行：

`host    all        all         0.0.0.0/0       trust`

2. 修改`${PGDATA}/postgresql.conf`

修改`listen_addresses`属性：

`listen_addresses = '*'`

3. 重启PostgreSQL服务后生效

`${PG_HOME}/bin/pg_ctl restart -D ${PGDATA}`