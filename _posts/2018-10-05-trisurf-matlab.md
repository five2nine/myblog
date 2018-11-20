---
layout: post
title: matlab trisurf 함수를 사용하여 지형 그리기
date: 2018-10-05 23:55:00 +0900
author: 원성규
excerpt: 
categories:
- maps
tags:
- matlab
- trisurf
- geometry
keywords:
---

## 데이타 형식
[[geomap-matlab]]과 같이 [[point-cloud-meshlab-data]]에서 작성한 `xyzrgb`데이타를 로드하여 `xyz`를 사용한다.

## 그래프 출력

[[geomap-python]]과 같은 방식으로 들루네(Delaunay) 삼각 메쉬를 생성하고 내장 함수 trisurf를 사용하여 공간 삼각 메쉬로 확장한다. 사례와 같이 비정형 경계를 가지는 경우에 경계를 포함하는 메쉬의 형상은 왜곡된다.

```matlab
tri = delaunay(x,y);
h = trisurf(tri, x, y, z);
colormap(jet);
colorbar EastOutside
axis([min(x) max(x) min(y) max(y)])
```

## 출력물

![trisurf-matlab]({{site.baseurl}}/img/trisurf-matlab.png?raw=true)


