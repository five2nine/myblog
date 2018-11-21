---
layout: post
title: NodeJS 서버 기초
date: 2018-10-16 23:55:00 +0900
author: 원성규
excerpt: NodeJS 서버의 실행과 정지 명령을 소개한다.
categories:
- labview
tags: 
- labview
- gps
- http
- javascript
keyworkds:
---


### nodejs 서버 실행

#### Putty를 사용하여 Synology에서 pm2 설정

```
npm uninstall orientjs
sudo npm install pm2 -g
which pm2
sudo ln -s /volume1/@appstore/Node.js_v8/usr/local/bin/pm2 pm2
```

#### nodejs 서버 실행

```
cd /volume1/web/nodejs_server
pm2 start app_mysql.js --watch

cd /volume1/web/earth-master
pm2 start dev-server.js --watch

cd /volume1/web/nodejs
pm2 start main.js --watch --ignore-watch="db.json session/*"
```

#### nodejs 서버 정지

```
pm2 stop dev-server.js -- 8080 --watch
pm2 stop app_mysql.js --watch
```

#### nodejs 기타 명령

```
pm2 kill
pm2 list
pm2 log
pm2 start app_mysql.js -- 8080 --watch
```





