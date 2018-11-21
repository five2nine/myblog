---
layout: post
title: matlab scatter 함수를 사용하여 지형 그리기
date: 2018-09-15 23:55:00 +0900
author: 원성규
excerpt: 
categories:
- matlab
tags:
- matlab
- scatter
- geometry
keywords:
---

## 데이타 형식

[[point-cloud-meshlab-data]]에서 작성한 `xyzrgb`데이타를 로드하여 `xyz`를 사용한다.

## 그래프 출력

`scatter3d`를 사용하여 point cloud를 표현한다. 수심에 따른 색상 표현은 기본 기능을 사용한다. 컬러맵은 `jet`이며 `rainbow`를 나타한다.
```matlab
scatter3(x,y,z,12,z,'filled')
colormap(jet);
colorbar EastOutside
daspect([1 1 1])
```

다른 사람이 만든 colormap을 다운로드할 수 있다.

- [Red Blue Colormap][1]
- [bluewhitered][2]

## 출력물

![point-cloud-matlab]({{site.baseurl}}/img/scatter-matlab.png?raw=true)


[1]:https://kr.mathworks.com/matlabcentral/fileexchange/25536-red-blue-colormap
[2]:https://kr.mathworks.com/matlabcentral/fileexchange/4058-bluewhitered



