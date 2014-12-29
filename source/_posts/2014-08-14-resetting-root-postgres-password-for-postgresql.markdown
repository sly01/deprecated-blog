---
layout: post
title: "Resetting Root(postgres) Password for Postgresql"
date: 2014-08-14 20:57:30 +0300
comments: true
categories: 
---

1-**Stop postgresql service**
```
service postgresql stop
```
2-**Close the authentication system for root**
```
vi /etc/postgresq/pg_hba.conf
```
*Edit that line*

**local all all ident** --> **local all postgres trust**

3-**Start postgresql service**
```
service postgresql start
```

4-**Login postgres as a root of postgresql server**
```
su - postgres
```
```
psql -d template1 -U postgres
```
```
alter user postgres with password 'new_password';
```

5-**Revert the configuration**

```
vi /etc/postgresql/pg_hba.conf
```

*Edit that line again*

**local all postgres trust** --> **local all all ident**

6-**Restart postgresql service**

```
service postgresql restart
```

