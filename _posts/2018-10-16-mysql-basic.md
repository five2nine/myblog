---
layout: post
title: MySQL 기본 명령
date: 2018-10-16 23:50:00 +0900
author: 원성규
excerpt: MySQL 기본 명령을 소개한다.
categories:
- labview
tags: 
- labview
- gps
- http
- javascript
keyworkds:
---

### mysql 기본 명령

#### mysql 구동

```
mysql.exe -hlocalhost -uroot -p
```

#### mysql database 목록

```
show databases;
```

#### mysql database 생성

```
CREATE DATABASE homedb CHARACTER SET utf8 COLLATE utf8_general_ci;
```

#### mysql database 생성 확인

```
show databases;
```

#### mysql database 사용

```
use homedb;
```

#### mysql database table 생성

```
CREATE TABLE topic (
    id int(11) NOT NULL AUTO_INCREMENT,
    title varchar(100) NOT NULL,
    description text NOT NULL,
    author varchar(30) NOT NULL,
    PRIMARY KEY (id)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
show tables;
```

#### mysql database table item 삽입

```
INSERT INTO topic (title, description, author) VALUES('JavaScript','Computer language for web.', 'egoing');
INSERT INTO topic (title, description, author) VALUES('NPM','Package manager', 'leezche');
```

#### mysql database table 생성

```
CREATE TABLE users ( 
    id INT NOT NULL AUTO_INCREMENT , 
    authId VARCHAR(50) NOT NULL ,
    username VARCHAR(30), 
    password VARCHAR(255), 
    salt VARCHAR(255),
    displayName VARCHAR(50),
    email VARCHAR(50) NOT NULL , 
    PRIMARY KEY (id), 
    UNIQUE (authId)
) ENGINE = InnoDB;
```

#### mysql database table 읽기

```
SELECT * FROM users \G
```

#### mysql database 이동 1 추출

```
mysql.exe -hlocalhost -uroot -p
show databases;
exit
mysqldump.exe -uroot -p homedb > homedb.sql
```

#### mysql database 이동 2 복원

```
mysql.exe -hlocalhost -uroot -p
CREATE DATABASE homedb CHARACTER SET utf8 COLLATE utf8_general_ci;
exit
mysqldump.exe -uroot -p homedb < homedb.sql
```



