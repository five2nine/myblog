---
layout: post
title: JSON 변환기
date: 2018-09-24 23:55:00 +0900
author: 원성규
excerpt: 
categories:
- maps
tags:
- javascript
- nomads
keywords:
---

## JSON 변환기

JSON 변환기는 [기후데이타](http://nomads.ncep.noaa.gov)를 JSON 형식으로 변환하는 Java 프로그램이다. Java 프로젝트 매니저 maven으로 관리된다.

`변환기`
https://github.com/cambecc/grib2json

`빌드`

```
set JAVA_HOME=C:\Program Files\Java\jdk1.8.0_181
cd grib2json-master
mvn package
```
