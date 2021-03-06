---
layout: post
title: 랩뷰 실시간 GPS 정보
date: 2018-11-19 20:40:00 +0900
author: 원성규
excerpt: 랩뷰에서 실시간으로 GPS 정보를 출력하기 위한 방안을 조합하고 있다.
categories:
- labview
tags: 
- labview
- gps
- http
- javascript
keyworkds:
---

### GPS 위성 분포를 웹브라우저에 표시하기 테스트

웹서버에서 위성 분포 파일을 제공한다.
웹서버에서 직접 GPS를 읽을 수 있으면 다른 프로그램이 필요없다.
위성 분포 파일은 5초마다 내용이 바뀐다. 혹은 파일이 교체된다.
위성 분포 파일은 랩뷰에서 GPS를 읽어서 기록한다.
데이타에 값의 변화가 잘 보이게 랜덤 노이즈를 섞는다.

웹브라우저에서 5초마다 위성 분포 파일을 가져온다.
웹브라우저에서 가져온 위성 분포 파일을 그래픽 또는 테이블로 화면에 표시한다.
웹브라우저에서 D3JS를 사용하여 스카이플롯을 그릴 수 있다.

### GPS 현재 위치를 웹브라우저에 표시하기 테스트

웹서버에서 현재 위치 파일을 제공한다.
웹서버에서 직접 GPS를 읽을 수 있으면 다른 프로그램이 필요없다.
위성 분포 파일은 1초마다 내용이 바뀐다. 혹은 파일이 교체된다.
위성 분포 파일은 랩뷰에서 GPS를 읽어서 기록한다.
데이타에 값의 변화가 잘 보이게 랜덤 노이즈를 섞는다.

웹브라우저에서 1초마다 현재 위치 파일을 가져온다.
웹브라우저에서 가져온 현재 위치 파일을 그래픽 또는 테이블로 화면에 표시한다.
웹브라우저에서 구글맵스 API를 사용하여 지도 상에 이동 경로를 표시할 수 있다.


### 랩뷰 웹브라우저 객체

랩뷰에 놓을 수 있는 웹브라우저 객체는 사용 용도가 제한적이다. 현재는 웹주소의 그림을 화면에 뿌리는 기능뿐이다.
웹브라우저 객체에서 일반 웹브라우저와 같이 자바스크립트를 사용할 수 있는 환경이 되고 HTTP 통신이 가능하다면 
수집된 다양한 정보를 웹 리소스와 겹쳐서 다이나믹하게 보여줄 수 있을 것이다.

현재의 랩뷰 환경에서는 웹 리소스(맵)와 추가 정보를 섞어서 보여줄 방법이 충분하지 않다.
랩뷰 NXG 차기 버전에서는 웹과 연동이 잘 될 것으로 파악되었다. 
2020년 이후에는 기존 랩뷰가 래거시로 남고 랩뷰 NXG가 주류가 될 수도 있다.


### 랩뷰 HTTP 통신

랩뷰 HTTP GET 통신 모듈을 사용하면 클라이언트 역할을 하여 JSON 서버에 요청하여 준비된 JSON 파일을 가져올 수 있다.
이렇게 하면 각지에 흩어져 있는 원격 데이타 서버에서 날씨 정보를 모아오는 역할을 할 수 있다.
자바스크립트를 사용하여 화면에 그래픽을 추가하는 작업과는 무관하다.


### 랩뷰 자바스크립트

액티브액스를 사용하여 자바스크립트가 적용된 웹페이지를 랩뷰 프론트에 나타내는 것이 가능하다는 것을 알았다.
현재 확보한 예제는 스태틱한 그래프를 화면에 보여주는데 VI가 종료된 뒤에 자바스크립트에 의해서 그래프가 인터액티브하게 반응하는 것을 보여주었다.
매 초당 좌표가 추가되면서 궤적을 업데이트하는 과정을 보여줄 수 있을런지는 아직 모르겠다.

웹브라우저 객체가 자바스크립트를 처리할 수 있을 정도로 최신 버전일 때 자바스크립트를 포함한 웹문서를 자바스크립트와 함께 실행하는 방식으로 파악되었다.
액티브액스를 사용하는 것은 부차적인 것으로 보인다. 기존에 사용하던 웹브라우저 객체는 단순한 정적 차트를 표시하는 데에 문제가 없지만 D3를 사용하하거나 구글맵스 API를 사용하는데에 문제가 있다.
다른 웹브라우저 객체를 가져올 수 있을지는 모르겠다.

구글맵스 자바스크립트 API 최소 적용하여 정적 지도와 같은 화면을 요청하여도 랩뷰 웹브라우저 객체는 처리하지 못한다.
이 객체는 버전이 낮은 인터넷 익스플로러의 액티브액스 객체인 것으로 보인다.

메타코드를 포함해서 구글맵스 API는 인식이 되었다. 인터넷익스플로러 기본 호환 버전이 7이어서 작동하지 않은 것이었다.
크롬과 같은 다른 웹브라우저를 액티브액스와 같은 방식으로 불러올 방법은 찾지 못했다.
```
<meta http-equiv="X-UA-Compatible" content="IE=11" >
```

### 랩뷰 HTTP 서버

랩뷰에서 제공하는 HTTP 통신은 랩뷰 프론트 화면과 닮게 자동 생성된 웹문서를 웹서버에서 제공한다. 
이제 제시된 웹주소에 접근하면 웹클라이언트와 랩뷰 프론트가 서로 동기화되어 움직이게 할 수 있다.
웹클라이언트에서 랩뷰 시스템에 명령을 전달할 수 있게 된 것이다.

### 랩뷰 TCP 통신

서버 VI에서 500ms마다 랜덤 숫자 50개 (400Byte)를 TCP 포트에 출력하고 클라이언트 VI에서 1000ms마다 그것을 읽는다.
서버 VI에서 생성된 데이타의 절반은 버려지고 절반은 클라이언트 VI에 전달된다.

이제 동일한 클라이언트 VI를 하나더 실행했을 때 서버 VI에 멀티 접속이 된다면 초당 두 번 출력되는 서버 데이타를 두 개의 클라이언트 VI에서 나누어 받을 수 있을 것이다. 
그러나 실제로는 클라이언트 VI 하나만 위와 같이 반응했고 두 번째 클라이언트 VI는 아무런 반응을 하지 않았다.

아마도 TCP 통신에서 서버 VI와 클라이언트 VI는 일대일로 묶여있는 모양이다. 이 연결은 통신중에 끊기지 않을 것으로 보인다. HTTP 통신에서는 클라이언트의 요청에 서버가 응답하고 바로 통신이 끊어지며 여러 클라이언트가 차례로 접속하여 데이타를 전송 받을 수 있는 것과는 구별된다.

### 랩뷰 실시간 GPS 

GPS를 실시간으로 랩뷰 프론트에 그리기 방안
- GPS 현재값을 파일에 저장
- GPS 현재값을 웹서버가 가져가서 HTTP로 제공
- 웹브라우저가 웹서버에서 GPS 현재값을 가져와서 경로에 추가

GPS 현재값을 웹서버가 가져가서 HTTP로 제공
- 랩뷰 TCP 통신은 동기화 통신으로서 현재 상황을 해결할 수 없음
- 랩뷰 웹서버는 랩뷰 인터페이스 전용으로 생각됨
- 랩뷰에서 일반 용도의 웹서버를 제공하지 않음
- 제 2의 웹서버를 운용할 수 있음

예상되는 구성
- 랩뷰에서 GPS 수집함
- 웹서버에 현재값을 주기적으로 제공함
- 랩뷰에 등록된 웹브라우저에서 자바스크립트로 웹서버의 현재값을 주기적으로 가져감

### 랩뷰 웹서비스

랩뷰 웹서비스는 메소드 VI를 작성했을 때 대응하는 접속 URL로 클라이언트가 접속할 수 있는 방식이다.
메소드 VI 하나당 GET 또는 POST 방식으로 랩뷰 서버가 명령을 받을 수 있다.
출력 메소드 VI를 작성하면 아이패드 모니터 프로그램으로 전용 UI를 사용하여 리포트 차트를 실시간으로 볼 수 있다.
조사해본 범위안에서는 일반 웹서버로서의 역할을 하지는 못하는 것으로 보인다.
따라서 구글 지도를 로딩하고 GPS 궤적을 나타내려면 별도의 웹서버를 만들어야할 것이다.

구글맵스 경로의 기존 경로는 로컬 파일을 불러오는 방식이었고 이 경우에는 추가 경로 정보를 전달할 방법이 없다.
이제 구글맵스 경로를 웹서버에 존재하는 웹문서에 연결시키면 서버에서 초기 화면 정보를 가져오고 이어서 AJAX로 추가 경로를 가져올 수 있는 가능성이 생겼다.
랩뷰 서버에서 AJAX가 가능한지는 모르지만 일반 웹문서를 제공할 수는 있었다.
이 경우 웹문서를 로딩하기 위해서 웹서비스를 시작해야 한다.
```
웹서비스-시작
```
구글맵스 경로를 공개컨텐츠폴더의 웹문서에 연결시키기 위한 사전 설정은 다음과 같다.
```
프로젝트-내컴퓨터-새로만들기-웹서비스
웹서비스-공개컨텐츠폴더추가
```

### 랩뷰 웹브라우저 객체

랩뷰 웹브라우저 객체는 인터넷 익스플로어의 기능을 가지며 지정된 웹문서를 객체의 브라우징 화면에 띄워준다. 아래의 문제 과정으로 랩뷰 프론트 패널에 실시간 지도 표시를 완료하였다.

- 정적 지도를 자바스크립트 API를 사용하는 지도를 호출하는 웹문서로 대체하였다.
- 구글맵스 API를 처리할 수 있는 IE-11 버전을 웹문서에 명시하였다.
- 랩뷰에서 웹서비스를 구동하였다.
- 지도 웹문서를 웹서버로 이동하고 웹문서의 위치로서 로컬 위치가 아니라 웹주소를 사용하였다.
- 테스트용 지도 좌표를 로딩하도록 AJAX를 사용하여 데이타 로딩하였다.
- 데이타 파일을 반복해서 읽을 때 크롬에서는 새 문서로 읽지만 IE-11에서는 수정되지 않은 이유(304)로 캐쉬에만 접근 가능하였다.
- 랩뷰 서버를 종료하고 일반 서버를 구동하였다.
- 웹문서 헤드에 포함될만한 메타 태크를 어떻게 써도 적용되지 않아서 서버를 교체하였다.


