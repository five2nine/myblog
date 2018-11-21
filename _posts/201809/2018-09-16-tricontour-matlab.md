---
layout: post
title: matlab tricontour 함수를 사용하여 지형 그리기
date: 2018-09-16 23:55:00 +0900
author: 원성규
excerpt: 
categories:
- matlab
tags:
- matlab
- tricontour
- geometry
keywords:
---

## 데이타 형식
[[geomap-matlab]]과 같이 [[point-cloud-meshlab-data]]에서 작성한 `xyzrgb`데이타를 로드하여 `xyz`를 사용한다.

## 그래프 출력

[[geomap-python]]과 같은 방식으로 들루네(Delaunay) 삼각 메쉬를 생성하고 [Duane Hanselman][1]가 작성한 `tricontour` 함수를 사용하여 컨투어를 그린다. 컨투어필은 할 수 없지만 컨투어 단계 수만 입력하므로 쉽게 컨투어를 생성한다.
 
```matlab
[C,h]=tricontour(tri,x,y,z,40);
```

## 출력물

![tricontour-matlab]({{site.baseurl}}/img/tricontour-matlab.png?raw=true)


[1]:https://kr.mathworks.com/matlabcentral/fileexchange/38858-contour-plot-for-scattered-data?focused=5249779&tab=function

