---
layout: post
title: python scatter 함수를 사용하여 지형 그리기
date: 2018-09-15 23:55:00 +0900
author: 원성규
excerpt: 
categories:
- python
tags:
- anaconda
- python
- scatter
- geometry
keywords:
- anaconda
- python
- scatter
- geometry
---

## 실행환경
- `python` 명령행을 사용하면 별도의 그래프 창이 나타난다. 그래프가 동적으로 나타나지만 큰 데이타를 처리하지 못한다.
- `jupyter` 웹인터페이스를 사용하면 인라인 그래프가 나타난다. 이 그래프는 정적인 그래프이다.
```bash
python point_cloud_python.py 
```

## Annotation Centents
데이타를 선택했을 때 보여줄 정보의 내용을 생성한다. 여기서는 3 좌표의 값이다.
```python
def update_annot(ind):
    pos = sc.get_offsets()[ind["ind"][0]]
    annot.xy = pos
    text = "{}\n{}\n{}".format('Lon=%7.3f'%x[ind["ind"][0]], 
                               'Lat=%7.3f'%y[ind["ind"][0]],
                               'Dep=%7.3f'%z[ind["ind"][0]])
    annot.set_text(text)
    # annot.get_bbox_patch().set_facecolor(cmap(norm(c[ind["ind"][0]])))
    annot.get_bbox_patch().set_alpha(0.4)
```

## [Annotation Control][1]
데이타를 선택했을 때 그래프가 반응하도록 동작을 정의한다.
```python
def onactive(event):
    vis = annot.get_visible()
    if event.inaxes == ax:
        cont, ind = sc.contains(event)
        if cont:
            update_annot(ind)
            annot.set_visible(True)
            fig.canvas.draw_idle()
        else:
            if vis:
                annot.set_visible(False)
                fig.canvas.draw_idle()
```

## Scatter 3D 모듈
```python
from mpl_toolkits.mplot3d import Axes3D
import matplotlib.pyplot as plt
import numpy as np
import os
```

## Data 로딩
텍스트 데이타를 쉽게 읽을 수 있다. 변수 3개를 한번에 할당하기 위해서 배열을 전치시켰다. 데이타 수가 너무 많을 경우에 건너 뛰며 읽었다.
```python
os.chdir(r"C:\my_work\webapp\create-react-app\point-cloud-python")
datafile=open("geomap.txt",'r')
xyz=np.loadtxt(datafile).transpose()
x,y,z=xyz[0:3,::100]
```

## 3D 그림판
그림판에 3차원 좌표축을 준비한다.
```python
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
ax.set_xlabel('Longitude')
ax.set_ylabel('Latitude')
ax.set_zlabel('Depth')
# ax.view_init(elev=90, azim=-90) # 평면
```

## Scatter 3D
빨강-노랑-파랑 컬러맵을 사용하여 3차원 분포도를 그르고 컬러바를 추가한다.
```python
cm = plt.cm.get_cmap('RdYlBu')
sc = ax.scatter(x, y, z, s=5, c=z, cmap=cm, marker='o', alpha=0.6)
# sc = ax.scatter(x, y, z, s=5, c=z, cmap=cm, marker='o', alpha=0.6, edgecolor='none')
plt.colorbar(sc)
```

## Annotation View
데이타를 선택했을 때 보여줄 정보의 틀을 준비하고 초기값으로 보이지 않게 설정한다.
```python
annot = ax.annotate("", xy=(0,0), xytext=(20,20),textcoords="offset points",
                    bbox=dict(boxstyle="round", fc="w"),
                    arrowprops=dict(arrowstyle="->"))
annot.set_visible(False)
```

## Annotation Event
데이타를 선택하는 이벤트를 결정한다.

마우스| 클릭 | 호버링
:------:|:-----------:|:-----------:
이벤트 | button_press_event | motion_notify_event

```python
fig.canvas.mpl_connect('button_press_event', onactive)
# fig.canvas.mpl_connect("motion_notify_event", onactive)
```

## 그림판 보이기
```python
plt.show()
```

## 출력물
![point-cloud-python]({{site.baseurl}}/img/scatter-python.png?raw=true)



[1]: https://stackoverflow.com/questions/10374930/matplotlib-annotating-a-3d-scatter-plot

