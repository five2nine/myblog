---
layout: post
title: python tricontourf 함수를 사용하여 지형 그리기
date: 2018-10-12 23:55:00 +0900
author: 원성규
excerpt: 
categories:
- python
tags:
- anaconda
- python
- tricontourf
- geometry
keywords:
---

## DAT 파일 로딩
```python
import numpy as np
datafile=open("geomap.txt",'r')
xyz=np.loadtxt(datafile).transpose()
x,y,z=xyz[0:3,::]
```

## 삼각형 맵생성
[들루네(Delaunay)][1] 삼각형 맵을 생성한다. 
```python
import matplotlib.tri as tri
triang = tri.Triangulation(x, y)
min_radius = 0.25
triang.set_mask(np.hypot(x[triang.triangles].mean(axis=1),
                         y[triang.triangles].mean(axis=1))< min_radius)
```

## 그림판 생성
그림판의 크기는 `figsize` 1 마다 72px이다.
```python
import matplotlib.pyplot as plt
fig1, ax1 = plt.subplots(figsize=(10,10))
ax1.set_aspect('equal')
ax1.set_title('geomap')
ax1.set_xlabel('East (meter)')
ax1.set_ylabel('North (meter)')
```

## 컨투어 라인 생성
```python
tcf = ax1.tricontour(triang, z, 40, colors='k', linewidths=0.3)
```

## 컨투어 채움 생성
컬러맵으로 무지개색을 사용한다.
```python
tcf = ax1.tricontourf(triang, z, 40, cmap='jet')
```

## 컬러바 생성
현재 축에 설정된 컬러맵을 사용한다.
```python
fig1.colorbar(tcf)
```

## [그림 파일 출력][2]
SVG 파일은 현재 라벨과 제목 텍스트 출력이 안된다.
PNG와 같은 고정 크기의 그림 파일은 그림판의 크기에 영향을 받는다.
```python
fig1.savefig('geomap.svg', format='svg')
fig1.savefig('geomap.pdf', format='pdf')
fig1.savefig('geomap.pdf', format='pdf')
```

## [그림에 한글 문자 출력][3]
```python
import matplotlib as mpl
import matplotlib.font_manager as fm
font_location = r'C:\Windows\Fonts\NGULIM.TTF'
font_name = fm.FontProperties(fname = font_location).get_name()
mpl.rc('font', family = font_name)
```

## 출력물
![geomap]({{site.baseurl}}/img/tricontourf-python.png?raw=true)

[1]:https://matplotlib.org/api/_as_gen/matplotlib.pyplot.tricontourf.html
[2]:https://matplotlib.org/api/_as_gen/matplotlib.pyplot.savefig.html
[3]:http://corazzon.github.io/matplotlib_font_setting
