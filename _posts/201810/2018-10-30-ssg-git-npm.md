---
layout: post
title: 정정 사이트 생성기 사용 중 메모
date: 2018-10-30 13:55:00 +0900
author: 원성규
excerpt: 
categories: Jekyll
tags:
- SSG
- Jekyll
- Gatsby
keywords:
- SSG
- Jekyll
- Gatsby
---

### 정적 사이트 생성기

정적 사이트 생성기(SSG, static site generator) 또는 정적 페이지 생성기는 문서 소스로부터 HTML 문서로 표시되는 홈페이지를 구성한다.
이 방식은 제한된 정보를 가지는 블로그나 설명서로 구성된 소규모 홈페이지를 구성할 때 유용하다.
PWA, Hot reloading, SSR 등 다양한 기능을 제공한다. 

GitHub pages에 사이트를 생성할 때 Jekyll을 사용하면 마크다운 소스를 직접 등록해야 했고, Gatsby를 사용하면 마크다운 소스를 HTML로 빌드하여 등록해야 했다.

생성기 | 기반 기술
----|-------
Jekyll | Ruby
Gatsby | React
Hexo | Node.js
Hugo | Go


### 다른 사람의 Gatsby 소스 브랜치 가져오기

다른 사람의 저장소에서 Gatsby 소스 브랜치를 가져온다.

```sh
git clone -b source https://github.com/wonism/wonism.github.io
```

`-b source` 옵션이 없으면 기본으로 선택된 `master` 브랜치를 가져온다.

```sh
git clone https://github.com/wonism/wonism.github.io
```

### 리모트 저장소 설정

사용할 리모트 저장소는 `https://github.com/five2nine/blog`의 `gh-pages` 브랜치이다.
`gh-pages` 브랜치가 `github pages`로 작동하도록 설정하였다. 
`github pages` 접속 주소는 https://five2nine.github.io/blog이다.

### Gatsby 프로젝트로 작업 내용를 바꾸기 위해 github 리모트 저장소 변경

```sh
git remote remove origin
git remote add origin https://github.com/five2nine/blog
git remote -v
```

### Gatsby 프로젝트를 github 저장소에 등록하기 위한 스크립트 실행

여기서 마크다운 문서의 yaml 헤더에 keywords 입력되지 않아서 에러가 발생했다. 문서마다 tags와 같은 keywords를 추가하여 에러를 없앴다.
스크립트는 빌드 폴더인 `.cache`와 `public`를 비우고 새로 빌드된 `public` 폴더를 `gh-pages` 브랜치에 등록한다.

```json
// package.json

{
	"scripts": {
		...
		"deploy": "rm -rf .cache/ && rm -rf public/ && gatsby build && gh-pages -d public -b gh-pages",
	}
}
```

### GitHub page

GitHub page에는 대표주소와 프로젝트 주소가 있다. 계정 이름이 username이면 대표 주소와 저장소는 각각 아래와 같다.

- 대표 주소: username.github.io
- 저장소: github.com/username/username.github.io

username 계정에 blog라는 프로젝트가 포함되었고 github pages 설정이 되었다면 blog 프로젝트 주소와 저장소는 각각 아래와 같다.

- 프로젝트 주소: username.github.io/blog
- 저장소: github.com/username/blog


### yaml 표기

마크다운 문서의 상단에 두 개의 `---` 라인 사이에 `:`으로 구분되는 옵션 정보를 추가할 수 있다. 이 표기법을 yaml이라 하고 화면에 렌더링되지는 않는다.

### HTML 문서에 MathJax 수식 표현

HTML 문서의 헤더에 아래 스크립트를 삽입하면 Latex 수식을 표시할 수 있다.

```html
<script type="text/javascript"  src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
```

마크다운 문서의 yaml 헤더에 포함시키는 방법은 불명확하다.
```yaml
html header:  <script type="text/javascript"  src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
```

### npm 모듈 설치

npm 특정 모듈에 특정 버전을 지정하여 설치

```
npm install gatsby@2.0.31
```

npm 특정 모듈에 최신 버전을 지정하여 설치

```
npm install gh-pages@*
```

package.json에 등록된 대로 설치

```
npm install
```

package.json에 등록된 모듈을 모두 최신 버전으로 개정

npm-check를 global로 설치하고 업데이트 한다.

```
npm update
```

### vscode에서 git bash 터미널 사용

```
// C:\Users\fabre\AppData\Roaming\Code\User\settings.json

"terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe",
"terminal.integrated.shellArgs.windows": [
"--login", "-i"
],
```

### 원격 저장소를 비우면서 현재 폴더를 업로드

`.git`을 제거하여 저장소 정보를 없애고 현재 폴더의 내용을 리모트 저장소에 강제로 덮어쓴다.
이것은 꼼수이며 저장소에 한 번 올라간 내용은 절대로 지워지지 않고 변경 내용으로 남는다. 
저장소를 초기화하는 방법은 저장소 자체를 지우는 방법뿐이다.

rm -rf .git
git init
git add .
git status
git commit -m "initial"
git remote add origin https://github.com/five2nine/five2nine.github.io
git remote -v
git push --force origin master

rm -rf .git
git init
git add .
git status
git commit -m "initial"
git remote add git https://github.com/five2nine/gblog
git remote -v
git push --force origin master


### 일반적인 프로젝트 원격 저장소 개정

git add .
git status
git commit -m "comment"
git push -u origin master


### 구글 어스 지면 오버레이

지면 오버레이를 사용하면 지구의 지형 위에 이미지를 '배치'할 수 있습니다.
경로 폴리라인 오버레이가 가능한지 알아보자.

https://developers.google.com/kml/documentation/kml_tut?hl=ko

https://developers.google.com/maps/documentation/javascript/examples/?hl=ko
https://developers.google.com/maps/documentation/javascript/examples/polyline-simple
https://developers.google.com/maps/documentation/javascript/examples/polyline-complex
https://developers.google.com/maps/documentation/javascript/reference/




### 구글 콘솔

https://console.cloud.google.com/getting-started?hl=ko&pli=1
https://console.developers.google.com/home/dashboard?project=rov-pos

Maps JavaScript API
API-KEY: AIzaSyA7Ms7Wq3QGGhqeQCF4VQyhzBYbVaqy-9E

Geocoding API
API-KEY: AIzaSyA7Ms7Wq3QGGhqeQCF4VQyhzBYbVaqy-9E 


### D3

https://www.bsidesoft.com/?p=2382
https://github.com/d3/d3/blob/master/CHANGES.md

https://medium.freecodecamp.org/learn-d3-js-in-5-minutes-c5ec29fb0725


https://medium.freecodecamp.org/learn-d3-js-in-5-minutes-c5ec29fb0725
https://scrimba.com/g/gd3js






index.html


<html>
    <head>
        <link rel="stylesheet" href="index.css">
        <title>Learn D3.js</title>
    </head>
    <body>
        <h1>SVG elements</h1>
        
        <svg></svg>
        
        <script src="https://d3js.org/d3.v4.min.js"></script>
        <script src="index.js"></script>
    </body>
</html>



const api = 'https://api.coindesk.com/v1/bpi/historical/close.json?start=2017-12-31&end=2018-04-01';







랩뷰 시리얼 통신
http://www.mylv.net/classes/study_view_popup.aspx?BID=118054&uid=psjhan93&qStr=p%3D1%26uid%3Dpsjhan93%26pS%3D20


랩뷰 NMEA - GPS library 1.0
https://forums.ni.com/t5/Example-Program-Drafts/NMEA-GPS-library/ta-p/3535972

랩뷰 NMEA - GPS library 1.1.2
https://forums.ni.com/t5/Example-Program-Drafts/New-NMEA-GPS-library/ta-p/3518883

랩뷰 Google Maps
https://forums.ni.com/t5/Example-Programs/Google-Maps-in-LabVIEW/ta-p/3512488


처리된 NMEA
GPGGA
GPGSV GLGSV
GNRMC GPRMC
GPVTG




시리얼 통신하기
NMEA 파싱하기 6종류
위성 분포 스카이플롯 그리기 - GPGSV GLGSV 사용
스카이플롯 격자 일반화하기
위성분포 2세트 그리기
버퍼링 대책 마련하기 
지도에 현재 위치 표시하기 - GPGGA 사용
시작하면 스카이플롯 초기화하기
스카이플롯 불필요한 화면 없애기
루프 속도 조절하기
위성분포에 그룹이름 보이기
지도 기능 간소화
시작 누르면 시작하고 종료 누르면 종료하기
시작하면 지도 그림 자동 다운로드 안하기 - 못막음
메시지가 하나도 안들어오면 종료하기
메시지를 웹서버에 올리기 (랩뷰 2018과 NXG 2.0 이상 필요. NXG는 cRIO 지원 안함. 랩뷰 웹서버는 디스플레이가 아니라 데이타 수집용)
지도 업데이트 온오프하기
위성 위치에 위성 번호 달기 (위성 번호를 주석으로 입력하려니까 아직도 리팩토링이 덜 되어었다)
랩뷰 웹브라우저 객체가 자바스크립트를 알고 있는가. 모른다.
통신 포트 버퍼링 확인하기
현재 시각과 메시지 생성 시각 일치여부 확인하기


메시지 로깅
통신 케이스를 상태 머신에 맞게 분할 조정하기 (상태머신 - 큐 메시지 핸들러)





랩뷰 웹통신
https://www.youtube.com/watch?v=6denRNUARCY

랩뷰 시리얼통신
https://www.youtube.com/watch?v=26-j-MK9Atw

랩뷰 디자인 패턴
기능적 글로벌 변수
상태 머신
이벤트 드리븐
https://www.youtube.com/watch?v=0Lnc3-au4iw


랩뷰 5분 40강
https://www.youtube.com/watch?v=IOkoyuikj5Q&list=PLdNp0fxltzmPvvK_yjX-XyYgfVW8WK4tu


NXG 고속 이미지
https://www.youtube.com/watch?v=M4CRZI86a9Y

극심한 노이즈 환경에서의 데이터 측정 기술
http://www.ni.com/newsletter/51921/ko/

박성준 강의실
http://www.mylv.net/classes/study_view_popup.aspx?BID=116813&uid=psjhan93&qStr=p%3D1%26uid%3Dpsjhan93%26pS%3D20

http://www.mylv.net/classes/study_list_popup.aspx?p=1&uid=psjhan93&pS=20






지도 데이타 다루는 방법
http://blog.hkwon.me/draw-korean-map-chart-with-geojson/








저속 항법
침매터널 함체 공사중 위치 확보
수중 포지셔닝






지킬 서버가 시작할 때 결정
모든 마크다운을 웹문서로 변환함
지킬 아카이브 페이지를 항목별로 생성하느냐 마느냐 
생성된 페이지 목록을 표시하느냐 마느냐 
아카이브 페이지에는 
목록 페이지
카테고리 페이지
태그 페이지
고유 페이지 (어바웃 타이포)















































