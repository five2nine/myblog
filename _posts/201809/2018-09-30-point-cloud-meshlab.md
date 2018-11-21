---
layout: post
title: mashlab 지형 그리기
date: 2018-09-30 23:55:00 +0900
author: 원성규
excerpt: 
categories:
- maps
tags:
- mashlab
- point cloud
- geometry
keywords:
---

## 데이타 형식

데이타 가져오기 메뉴에서 텍스트 또는 가능한 모든 형식으로 파일을 지정한다.
테스트 데이타는 `위도`, `경도`, `수심`으로 구성되었는데 매트랩에서 `UTM` 좌표로 변경하고 수심을 컬러맵에 매핑하여 `xyzrgb` 형식으로 출력하고 meshlab에서 임포트하였다.

- `xyz`만 포함하는 데이타 세트
    - 자동으로 3차원 좌표로 인식하고 기본 색상이 지정

- `xyz`와 함께 `rgb`를 포함한 데이타 세트
    - 데이타 형식을 xyzrgb로 지정
    - 구분자(semicolon, comma, space)를 지정
    - 색상 범위(int32:255 또는 float64:1.0)를 지정

## 화면 조정

기능 | 방법
-----:|:-----
회전 | left mouse 
확대 | mouse wheel
확대 | alt + left mouse 
회전 | alt + middel mouse 
포인트 크기 변경 | alt + mouse wheel
확대 | shift + left mouse 
투영각 | shift + mouse wheel
평행 이동 | ctrl + left mouse 

## 절점 정보 표시

기능 | 방법
-----:|:-----
경계 박스 표시 | bounding box icon
좌표 읽기 | information icon
좌표 읽기 전환 | space while information icon
화면 조정 모드 복귀 | global icon
스케일 확대 | transform scala normalize menu

## 프로젝트 파일 저장

- `xyz`만 포함하는 데이타 세트
    - 저장하면 새로 프로젝트 파일(`*.mlp`)을 생성
    - 포함된 3D mesh 객체를 자동으로 새 파일(`*.ply`)로 저장
    - 3D mesh 객체를 프로젝트에 등록
- `xyz`와 함께 `rgb`를 포함한 데이타 세트
    - `export mesh as` 메뉴를 사용하여 수동으로 3D mesh 객체를 `*.ply` 파일로 저장
    -  저장 내용에 절점 색상을 포함(기본 선택)
    - 프로젝트 파일을 생성하면 방금 저장한 객체를 포함하여 저장

## 출력물

![point-cloud-meshlab]({{site.baseurl}}/img/point-cloud-meshlab.png?raw=true)


