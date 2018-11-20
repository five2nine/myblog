---
layout: post
title: sensitivity 적용
date: 2018-10-23 23:55:00 +0900
author: 원성규
excerpt: 
categories:
- labview gps
tags:
- sensitivity
- labview
- ni
keywords:
---

## 센시티비티(sensitivity) 적용
AI(analog input) 모듈에서 측정된 전압을 물리량으로 변환하기 위해 센시티비티를 사용한다. 예를 들면 센시티비티가 4 mV/m/s<sup>2</sup>인 가속도계에서 측정된 전압이 4 mV이면 전압을 센시티비티로 나누어서 1 m/s<sup>2</sup>을 얻게 된다.

그러나 실제로 측정되는 값의 단위는 `mV`가 아니라 `V`이므로 실제로 물리량을 환산할 때는 다음과 같이 V로 환산된 값이 사용된다.

>( 0.004 V ) / ( 0.004 V/m/s<sup>2</sup> ) = ( 1 m/s<sup>2</sup> )


