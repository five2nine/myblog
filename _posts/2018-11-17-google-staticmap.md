---
layout: post
title: 구글 정적 지도
date: 2018-11-17 09:05:00 +0900
author: 원성규
excerpt: 
categories:
- google
tags:
- google
- maps
keywords:
---

구글 정적 지도는 HPPT GET을 통해 전송된 지역 지도를 구글에서 빌드된 그림파일로 전송받아서 화면에 보여주는 방식을 사용한다. 여기서는 부산 한국해양과학기술원을 중심으로 몇개의 정적 지도 예시를 보인다.

### 구글 정적 지도

주요 지리
```
한국해양과학기술원,35.074979,129.076492
한국해양과학기술원 제2연구동,35.075906,129.079660
절영아파트,35.075292,129.067594
```

절영아파트

![절영아파트](https://maps.google.com/maps/api/staticmap?zoom=16&size=640x400&key=AIzaSyCRJTyXL0g6x8KOfjPVXr0B6P1-pqc0a54&center=35.075292,129.067594)

```html
<img src="https://maps.google.com/maps/api/staticmap?zoom=16&size=640x400&key=AIzaSyCRJTyXL0g6x8KOfjPVXr0B6P1-pqc0a54&center=35.075292,129.067594">
```

한국해양대학교

![한국해양대학교](https://maps.google.com/maps/api/staticmap?zoom=16&size=640x400&key=AIzaSyCRJTyXL0g6x8KOfjPVXr0B6P1-pqc0a54&center=해양대)

```html
<img src="https://maps.google.com/maps/api/staticmap?zoom=16&size=640x400&key=AIzaSyCRJTyXL0g6x8KOfjPVXr0B6P1-pqc0a54&center=해양대">
```

한국해양과학기술원

![한국해양과학기술원](https://maps.google.com/maps/api/staticmap?zoom=16&size=640x400&key=AIzaSyCRJTyXL0g6x8KOfjPVXr0B6P1-pqc0a54&center=35.074979,129.076492)

```html
<img src="https://maps.google.com/maps/api/staticmap?zoom=16&size=640x400&key=AIzaSyCRJTyXL0g6x8KOfjPVXr0B6P1-pqc0a54&center=35.074979,129.076492">
```

한국해양과학기술원

![한국해양과학기술원](https://maps.google.com/maps/api/staticmap?center=35.074979,129.076492&key=AIzaSyCRJTyXL0g6x8KOfjPVXr0B6P1-pqc0a54&zoom=16&size=640x400&maptype=hybrid&markers=icon:http://lavag.org/public/style_extra/forum_imgs/LV.png&#124;35.077436,129.076580&#124;35.077546,129.078037)

```html
<img src="https://maps.google.com/maps/api/staticmap?center=35.074979,129.076492&key=AIzaSyCRJTyXL0g6x8KOfjPVXr0B6P1-pqc0a54&zoom=16&size=640x400&maptype=hybrid&markers=icon:http://lavag.org/public/style_extra/forum_imgs/LV.png&#124;35.077436,129.076580&#124;35.077546,129.078037">
```

파이프라인 문자는 마크다운에서 먼저 테이블 구분자로 변환된다. 파이프라인 문자 깨짐 현상의 해법은 다음과 같다.
- 이스케이프 문자인 `&#124;`로 바꾸어 사용
- HTML 이미지 `img` 태그 사용

한국해양과학기술원

![한국해양과학기술원](
https://maps.google.com/maps/api/staticmap?center=35.075906,129.079660&key=AIzaSyCRJTyXL0g6x8KOfjPVXr0B6P1-pqc0a54&zoom=17&size=640x400&maptype=satellite&path=weight:3|color:0xFF0000|35.074898,129.079857|35.074897,129.079856|35.074916,129.079850|35.074861,129.079915|35.074725,129.079854|35.074511,129.079745|35.074296,129.079306|35.074571,129.078892|35.075080,129.078542|35.075500,129.078247|35.075961,129.077930|35.076305,129.078384|35.076584,129.078941|35.076949,129.079700|35.077236,129.080331|35.077376,129.080772|35.076955,129.081266|35.076379,129.081650|35.075852,129.082009|35.075456,129.081792|35.075110,129.081043&markers=size:small|35.075110,129.081043)

```html
<img src="https://maps.google.com/maps/api/staticmap?center=35.075906,129.079660&key=AIzaSyCRJTyXL0g6x8KOfjPVXr0B6P1-pqc0a54&zoom=17&size=640x400&maptype=satellite&path=weight:3|color:0xFF0000|35.074898,129.079857|35.074897,129.079856|35.074916,129.079850|35.074861,129.079915|35.074725,129.079854|35.074511,129.079745|35.074296,129.079306|35.074571,129.078892|35.075080,129.078542|35.075500,129.078247|35.075961,129.077930|35.076305,129.078384|35.076584,129.078941|35.076949,129.079700|35.077236,129.080331|35.077376,129.080772|35.076955,129.081266|35.076379,129.081650|35.075852,129.082009|35.075456,129.081792|35.075110,129.081043&markers=size:small|35.075110,129.081043">
```

한국해양과학기술원 

![한국해양과학기술원](
https://maps.google.com/maps/api/staticmap?center=35.075906,129.079660&key=AIzaSyCRJTyXL0g6x8KOfjPVXr0B6P1-pqc0a54&zoom=17&size=640x400&maptype=satellite&path=weight:3|color:0xFF0000|35.074898,129.079857|35.074898,129.079857|35.074898,129.079857|35.074898,129.079857|35.074898,129.079857|35.074898,129.079856|35.074898,129.079856|35.074898,129.079856|35.074898,129.079856|35.074898,129.079856|35.074897,129.079856|35.074897,129.079856|35.074897,129.079856|35.074897,129.079856|35.074897,129.079856|35.074902,129.079863|35.074902,129.079863|35.074902,129.079863|35.074902,129.079863|35.074902,129.079863|35.074916,129.079850|35.074916,129.079850|35.074916,129.079850|35.074916,129.079850|35.074916,129.079850|35.074904,129.079891|35.074904,129.079891|35.074904,129.079891|35.074904,129.079891|35.074904,129.079891|35.074861,129.079915|35.074861,129.079915|35.074861,129.079915|35.074861,129.079915|35.074861,129.079915|35.074784,129.079932|35.074784,129.079932|35.074784,129.079932|35.074784,129.079932|35.074784,129.079932|35.074725,129.079854|35.074725,129.079854|35.074725,129.079854|35.074725,129.079854|35.074725,129.079854|35.074609,129.079835|35.074609,129.079835|35.074609,129.079835|35.074609,129.079835|35.074609,129.079835|35.074511,129.079745|35.074511,129.079745|35.074511,129.079745|35.074511,129.079745|35.074511,129.079745|35.074426,129.079519|35.074426,129.079519|35.074426,129.079519|35.074426,129.079519|35.074426,129.079519|35.074296,129.079306|35.074296,129.079306|35.074296,129.079306|35.074296,129.079306|35.074296,129.079306|35.074328,129.079059|35.074328,129.079059|35.074328,129.079059|35.074328,129.079059|35.074328,129.079059|35.074571,129.078892|35.074571,129.078892|35.074571,129.078892|35.074571,129.078892|35.074571,129.078892|35.074835,129.078711|35.074835,129.078711|35.074835,129.078711|35.074835,129.078711|35.074835,129.078711|35.075080,129.078542|35.075080,129.078542|35.075080,129.078542|35.075080,129.078542|35.075080,129.078542|35.075269,129.078398|35.075269,129.078398|35.075269,129.078398|35.075269,129.078398|35.075269,129.078398|35.075500,129.078247|35.075500,129.078247|35.075500,129.078247|35.075500,129.078247|35.075500,129.078247|35.075721,129.078109|35.075721,129.078109|35.075721,129.078109|35.075721,129.078109|35.075721,129.078109|35.075961,129.077930|35.075961,129.077930|35.075961,129.077930|35.075961,129.077930|35.075961,129.077930|35.076182,129.078060|35.076182,129.078060|35.076182,129.078060|35.076182,129.078060|35.076182,129.078060|35.076305,129.078384|35.076305,129.078384|35.076305,129.078384|35.076305,129.078384|35.076305,129.078384|35.076434,129.078656|35.076434,129.078656|35.076434,129.078656|35.076434,129.078656|35.076434,129.078656|35.076584,129.078941|35.076584,129.078941|35.076584,129.078941|35.076584,129.078941|35.076584,129.078941|35.076773,129.079320|35.076773,129.079320|35.076773,129.079320|35.076773,129.079320|35.076773,129.079320|35.076949,129.079700|35.076949,129.079700|35.076949,129.079700|35.076949,129.079700|35.076949,129.079700|35.077106,129.080045|35.077106,129.080045|35.077106,129.080045|35.077106,129.080045|35.077106,129.080045|35.077236,129.080331|35.077236,129.080331|35.077236,129.080331|35.077236,129.080331|35.077236,129.080331|35.077327,129.080540|35.077327,129.080540|35.077327,129.080540|35.077327,129.080540|35.077327,129.080540|35.077376,129.080772|35.077376,129.080772|35.077376,129.080772|35.077376,129.080772|35.077376,129.080772|35.077227,129.081078|35.077227,129.081078|35.077227,129.081078|35.077227,129.081078|35.077227,129.081078|35.076955,129.081266|35.076955,129.081266|35.076955,129.081266|35.076955,129.081266|35.076955,129.081266|35.076673,129.081450|35.076673,129.081450|35.076673,129.081450|35.076673,129.081450|35.076673,129.081450|35.076379,129.081650|35.076379,129.081650|35.076379,129.081650|35.076379,129.081650|35.076379,129.081650|35.076110,129.081836|35.076110,129.081836|35.076110,129.081836|35.076110,129.081836|35.076110,129.081836|35.075852,129.082009|35.075852,129.082009|35.075852,129.082009|35.075852,129.082009|35.075852,129.082009|35.075612,129.082054|35.075612,129.082054|35.075612,129.082054|35.075612,129.082054|35.075612,129.082054|35.075456,129.081792|35.075456,129.081792|35.075456,129.081792|35.075456,129.081792|35.075456,129.081792|35.075299,129.081450|35.075299,129.081450|35.075299,129.081450|35.075299,129.081450|35.075299,129.081450|35.075110,129.081043|35.075110,129.081043|35.075110,129.081043|35.075110,129.081043|35.075110,129.081043|35.074940,129.080645|35.074940,129.080645|35.074940,129.080645|35.074940,129.080645|35.074940,129.080645|35.074754,129.080244|35.074754,129.080244|35.074754,129.080244|35.074754,129.080244|35.074754,129.080244|35.074589,129.079867|35.074589,129.079867|35.074589,129.079867|35.074589,129.079867|35.074589,129.079867&markers=size:small|35.074589,129.079867)

```html
<img src="https://maps.google.com/maps/api/staticmap?center=35.075906,129.079660&key=AIzaSyCRJTyXL0g6x8KOfjPVXr0B6P1-pqc0a54&zoom=17&size=640x400&maptype=satellite&path=weight:3|color:0xFF0000|35.074898,129.079857|35.074898,129.079857|35.074898,129.079857|35.074898,129.079857|35.074898,129.079857|35.074898,129.079856|35.074898,129.079856|35.074898,129.079856|35.074898,129.079856|35.074898,129.079856|35.074897,129.079856|35.074897,129.079856|35.074897,129.079856|35.074897,129.079856|35.074897,129.079856|35.074902,129.079863|35.074902,129.079863|35.074902,129.079863|35.074902,129.079863|35.074902,129.079863|35.074916,129.079850|35.074916,129.079850|35.074916,129.079850|35.074916,129.079850|35.074916,129.079850|35.074904,129.079891|35.074904,129.079891|35.074904,129.079891|35.074904,129.079891|35.074904,129.079891|35.074861,129.079915|35.074861,129.079915|35.074861,129.079915|35.074861,129.079915|35.074861,129.079915|35.074784,129.079932|35.074784,129.079932|35.074784,129.079932|35.074784,129.079932|35.074784,129.079932|35.074725,129.079854|35.074725,129.079854|35.074725,129.079854|35.074725,129.079854|35.074725,129.079854|35.074609,129.079835|35.074609,129.079835|35.074609,129.079835|35.074609,129.079835|35.074609,129.079835|35.074511,129.079745|35.074511,129.079745|35.074511,129.079745|35.074511,129.079745|35.074511,129.079745|35.074426,129.079519|35.074426,129.079519|35.074426,129.079519|35.074426,129.079519|35.074426,129.079519|35.074296,129.079306|35.074296,129.079306|35.074296,129.079306|35.074296,129.079306|35.074296,129.079306|35.074328,129.079059|35.074328,129.079059|35.074328,129.079059|35.074328,129.079059|35.074328,129.079059|35.074571,129.078892|35.074571,129.078892|35.074571,129.078892|35.074571,129.078892|35.074571,129.078892|35.074835,129.078711|35.074835,129.078711|35.074835,129.078711|35.074835,129.078711|35.074835,129.078711|35.075080,129.078542|35.075080,129.078542|35.075080,129.078542|35.075080,129.078542|35.075080,129.078542|35.075269,129.078398|35.075269,129.078398|35.075269,129.078398|35.075269,129.078398|35.075269,129.078398|35.075500,129.078247|35.075500,129.078247|35.075500,129.078247|35.075500,129.078247|35.075500,129.078247|35.075721,129.078109|35.075721,129.078109|35.075721,129.078109|35.075721,129.078109|35.075721,129.078109|35.075961,129.077930|35.075961,129.077930|35.075961,129.077930|35.075961,129.077930|35.075961,129.077930|35.076182,129.078060|35.076182,129.078060|35.076182,129.078060|35.076182,129.078060|35.076182,129.078060|35.076305,129.078384|35.076305,129.078384|35.076305,129.078384|35.076305,129.078384|35.076305,129.078384|35.076434,129.078656|35.076434,129.078656|35.076434,129.078656|35.076434,129.078656|35.076434,129.078656|35.076584,129.078941|35.076584,129.078941|35.076584,129.078941|35.076584,129.078941|35.076584,129.078941|35.076773,129.079320|35.076773,129.079320|35.076773,129.079320|35.076773,129.079320|35.076773,129.079320|35.076949,129.079700|35.076949,129.079700|35.076949,129.079700|35.076949,129.079700|35.076949,129.079700|35.077106,129.080045|35.077106,129.080045|35.077106,129.080045|35.077106,129.080045|35.077106,129.080045|35.077236,129.080331|35.077236,129.080331|35.077236,129.080331|35.077236,129.080331|35.077236,129.080331|35.077327,129.080540|35.077327,129.080540|35.077327,129.080540|35.077327,129.080540|35.077327,129.080540|35.077376,129.080772|35.077376,129.080772|35.077376,129.080772|35.077376,129.080772|35.077376,129.080772|35.077227,129.081078|35.077227,129.081078|35.077227,129.081078|35.077227,129.081078|35.077227,129.081078|35.076955,129.081266|35.076955,129.081266|35.076955,129.081266|35.076955,129.081266|35.076955,129.081266|35.076673,129.081450|35.076673,129.081450|35.076673,129.081450|35.076673,129.081450|35.076673,129.081450|35.076379,129.081650|35.076379,129.081650|35.076379,129.081650|35.076379,129.081650|35.076379,129.081650|35.076110,129.081836|35.076110,129.081836|35.076110,129.081836|35.076110,129.081836|35.076110,129.081836|35.075852,129.082009|35.075852,129.082009|35.075852,129.082009|35.075852,129.082009|35.075852,129.082009|35.075612,129.082054|35.075612,129.082054|35.075612,129.082054|35.075612,129.082054|35.075612,129.082054|35.075456,129.081792|35.075456,129.081792|35.075456,129.081792|35.075456,129.081792|35.075456,129.081792|35.075299,129.081450|35.075299,129.081450|35.075299,129.081450|35.075299,129.081450|35.075299,129.081450|35.075110,129.081043|35.075110,129.081043|35.075110,129.081043|35.075110,129.081043|35.075110,129.081043|35.074940,129.080645|35.074940,129.080645|35.074940,129.080645|35.074940,129.080645|35.074940,129.080645|35.074754,129.080244|35.074754,129.080244|35.074754,129.080244|35.074754,129.080244|35.074754,129.080244|35.074589,129.079867|35.074589,129.079867|35.074589,129.079867|35.074589,129.079867|35.074589,129.079867&markers=size:small|35.074589,129.079867">
```

