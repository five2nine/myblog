---
layout: post
title: matlab tricontf 함수를 사용하여 지형 그리기
date: 2018-10-13 23:55:00 +0900
author: 원성규
excerpt: 
categories:
- matlab
tags:
- matlab
- tricontf
- geometry
keywords:
---

## 데이타 형식

[[point-cloud-meshlab-data]]에서 작성한 `xyzrgb`데이타를 로드하여 `xyz`를 사용한다.

## 그래프 출력

[[geomap-python]]과 같은 방식으로 들루네(Delaunay) 삼각 메쉬를 생성하고 메쉬의 절점을 기준으로 컨투어필과 컨투어를 실시한다. 매트랩에서는 [Rich Pawlowicz][1]가 작성한 함수 `tricontf`와 `tricont`를 사용한다. 컬러맵으로 `jet`를 사용하고 색상 단계는 40개이다.
```matlab
scala=linspace(min(z),max(z),40);
tri = delaunay(x,y);

[CS,h]=tricontf(x,y,tri,z,scala);
set(h,'edgecolor','none');
hold on;

[CS,h]=tricont(x,y,tri,z,scala);
set(h,'linewidth',0.2,'edgecolor',rgb('black'))
hold off;

colormap(jet);
colorbar EastOutside
axis([min(x) max(x) min(y) max(y)])
```

## 출력물

![geomap-matlab]({{site.baseurl}}/img/tricontf-matlab.png?raw=true)



[1]:https://kr.mathworks.com/matlabcentral/fileexchange/40847-tricontf


