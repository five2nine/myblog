---
layout: post
title: create-react-app
date: 2018-10-08 23:55:00 +0900
author: 원성규
excerpt: 
categories:
- react
tags:
- react
- nodejs
keywords:
---

## 명령창

npm이 준비되었다면 cmd 명령창을 실행한다.

```
[wnidows] + r
cmd
```

`환경변수`에 아래의 `npm 경로`가 포함되어야 하는데 qdir 빠른 실행 명령창에는 환경변수에 경로가 적용되지 않는다.

```
C:\Users\fabre\AppData\Roaming\npm
```

## create-react-app

트위터에서 배포하는 `create-react-app` 모듈이 글로벌로 설치되어야 한다.

```
npm install -g create-react-app
```

## 프로젝트 생성

create-react-app 모듈을 사용하여 프로젝트를 생성한다. 아래를 실행하면 movie-app은 react-project 하위에 생성된다.

```
cd react-project
create-react-app movie-app
```

## 프로젝트 개발 웹서버

웹앱 서버 프로그램을 구동한다. 

```
cd movie-app
yarn start
```

