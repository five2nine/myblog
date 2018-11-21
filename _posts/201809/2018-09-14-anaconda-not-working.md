---
layout: post
title: Anaconda가 작동하지 않을 때
date: 2018-09-14
author: 원성규
excerpt: 
categories:
- python
tags: 
- anaconda
- error
keyworkds:
---

## ILnumeric 설치가 원인

ILnumeric WPF 라이브러리를 전날에 설치했었는데 여기에 포함된 `zip.lib`가 원인이되어 anconda가 작동하지 않았었다..


## seaborn 설치가 원인

python `conda` 매니저로 `seaborn` 패키지를 아래와 같이 설치하였다.
```
> run anaconda prompt
conda install -c anaconda seaborn 
```

이후 `anaconda`가 작동하지 않을 때 다음과 같은 시도를 하여 해결하였다.
요약하면 설치된 모듈들을 패키지 매니저를 사용하여 최신의 세트로 변경하였다. 최종 메시지는 인스톨 완료이다.

`상태확인`
```
conda info
conda list --show-channel-urls
anaconda-navigator
```

`업데이트`
```
conda update conda
conda update anaconda-navigator
conda update --all
```
