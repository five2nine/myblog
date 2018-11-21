---
layout: post
title: React on Github Pages
date: 2018-10-10 23:55:00 +0900
author: 원성규
excerpt: 
categories:
- react
tags:
- react
- github
- movieapp
keywords:
---

## React 앱작성

[[create-react-app]]으로 [[movie-app]] 작성한다.

## 저장소 생성

[Github Desktop][1]에 저장소를 생성한다. 로컬 하위 경로에 저장소 이름의 폴더를 생성되하거나 이미 존재하는 폴더를 저장소로 등록하게 된다. 단 기존의 폴더에서 `.git` 폴더를 지우면 로컬 정보가 초기화된다. 그리고 `node_modules`를 저장소에서 제외하기 위해서 제외 목록이 저장된 `.gitignore`를 포함해야 한다.

- `저장소 이름` movie-app
- `로컬 경로` C:\my_work\webapp\create-react-app\

새로 생성된 브랜치는 다음과 같다.

>`master`: https://github.com/five2nine/movie-app/tree/master

## Github Pages 생성

Github `Setup`에서 `Github Pages`로 master 브랜치를 지정한다.

## gh-pages 브랜치 생성

`packages.json`에 다음을 추가한다.
```
"homepage": "https://five2nine.github.io/movie-app",
"predeploy": "npm run build",
"deploy": "gh-pages -d build"
```

`정적 홈페이지`를 생성하고 Github에 새 브랜치로 등록한다.
```
npm install --save-dev gh-pages
npm run deploy
```

새로 생성된 브랜치는 다음과 같다.
>`gh-pages`: https://github.com/five2nine/movie-app/tree/gh-pages

## gh-pages 브랜치 생성

Github Setup에서 Github Pages를 master 브랜치에서 gh-pages 브랜치로 변경한다. 변경 내용이 적용되면 gh-pages 브랜치에 업로드된 index.html로 시작하는 정적 웹앱이 서비스된다.

>`movie-app`: https://five2nine.github.io/movie-app/

movie-app 웹앱은 클라이언트가 알고리즘과 DB서버의 주소를 가지고 있고 Github는 홉서버 서비스만 제공한다. Github는 Nodejs와 같은 동적 서버의 역할이나 DB서버의 역할을 하지 못한다.


[1]:https://desktop.github.com/

