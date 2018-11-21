---
layout: post
title: 깃허브에 지킬 업로드
date: 2018-11-20 20:40:00 +0900
author: 원성규
excerpt: 
categories:
- labview
tags: 
- labview
- gps
- http
- javascript
keyworkds:
---

깃허브에 지킬 블로그를 업로드할 때 필요한 일괄 작업이다.

### 지킬 초기 업로드

github 원격 레포지토리 연결 제거 
```sh
git remote remove origin
```

github 레포지토리 주소 연결
```sh
git remote add origin https://github.com/five2nine/myblog
```

Jekyll 블로그를 설치한 터미널로 이동 후 git 활성화
```sh
git init
```

블로그 폴더를 git staging 상태로 올리기
```sh
git add .
```

커밋 메세지 작성
```sh
git commit -m "init blog"
```

github에 파일 업로드
```sh
git push -u origin master
```

https://github.com/five2nine/myblog
페이지 설정에서 master를 깃허브페이지로 설정


### 지킬 변경 업로드

일괄 작업
- github 원격 레포지토리 연결 제거 
- github 레포지토리 주소 연결
- 블로그 폴더를 git staging 상태로 올리기
- 커밋 메세지 작성
- github에 파일 업로드

```sh
git remote remove origin
git remote add origin https://github.com/five2nine/myblog
git add .
git commit -m "changed"
git push -u origin master
```

