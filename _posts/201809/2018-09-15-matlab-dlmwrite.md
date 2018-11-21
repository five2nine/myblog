---
layout: post
title: matlab dlmwrite 함수로 행렬 쓰기
date: 2018-09-15 23:55:00 +0900
author: 원성규
excerpt: 
categories:
- matlab
tags:
- matlab
- iostream
keywords:
---

### dlmwrite 함수
matlab [dlmwrite][1] 함수는 ASCII로 파일에 구분자로 값이 구별되는 행렬을 일괄 저장한다.

탭 문자로 구분하고 세 자리 유효 자릿수의 정밀도를 사용하여 행렬 M을 'myFile.txt' 파일에 씁니다.
```matlab
dlmwrite('myFile.txt',M,'delimiter','\t','precision',3)
```
[1]:https://kr.mathworks.com/help/matlab/ref/dlmwrite.html


