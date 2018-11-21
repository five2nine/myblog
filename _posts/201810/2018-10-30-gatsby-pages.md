---
layout: post
title: 정적 사이트 생성기
date: 2018-10-30 12:55:00 +0900
author: 원성규
excerpt: 
categories:
- markdown
tags:
- SSG
- gatsby
- github
keywords:
---

인터넷 상의 대부분 홈페이지는 정적인 정보를 제공한다. 여기서 정적이라는 말은 서버가 클라이언트의 요쳥에 맞추어 실시간으로 데이타를 재구성할 필요가 없다는 말이다.

## Gatsby 정적 사이트

Gatsby는 정적 홈페이지를 만드는 도구이다. 소스 문서는 마크다운으로 작성하며 빌드단계에서 마크다운 문서는 HTML 문서로 변환되면서 CSS가 적용된다. 

루비 언어로 작성된 홈페이지 구조 명세가 HTML에 적용되고 문서간 네비게이션과 마크다운에 포함된 태그로 구별되는 문서 집합도 생성한다.

Gatsgy 작업 결과로서 홈페이지 리소스가 하나의 폴더에 모이면 이 폴더를 통채로 준비된 깃허브 저장소에 푸시한다. 

## Rinae's devlog

아래의 예시에서 홈페이지 저장소는 `adhrinae.github.io`이고 소스 문서의 저장소는 `gatsby-blog`이다.
홈페이지 소스 문서와 홈페이지 구성 파일이 각각 별도의 github 저장소에 올라있다. 

Gatsby로 만든 블로그형 홈페이지
https://adhrinae.github.io/

![Rinae-homepage-gatsby]({{site.baseurl}}/img/Rinae-homepage-gatsby.png)
*Rinae homepage screenshot*

홈페이지의 github 리포지토리
https://github.com/adhrinae/adhrinae.github.io

![Rinae-homepage-github-repo]({{site.baseurl}}/img/Rinae-homepage-github-repo.png)
*Rinae homepage deploy repository*


홈페이지 소스 문서의 github 저장소
https://github.com/adhrinae/gatsby-blog

![Rinae-homepage-source-github-repo]({{site.baseurl}}/img/Rinae-homepage-source-github-repo.png)
*Rinae homepage source repository*


## junhobaik

아래의 예시에서 홈페이지 소스 문서는 `master` 브랜치에 홈페이지 소스 문서는 `develop` 브랜치에 각각 올라있다. `username.github.io` 형식의 홈페이지는 `master` 브랜치에만 올라갈 수 있기 때문이다. 
완전히 다른 두 개의 브랜치를 하나의 프로젝트에 포함시켜 투트랙으로 관리하는 모양새이다.

Gatsby로 만든 블로그형 홈페이지
https://junhobaik.github.io/

![junhobaik-homepage-gatsby]({{site.baseurl}}/img/junhobaik-homepage-gatsby.png)

홈페이지의 github 리포지토리
https://github.com/junhobaik/junhobaik.github.io/tree/master

![junhobaik-homepage-github-repo]({{site.baseurl}}/img/junhobaik-homepage-github-repo.png)

홈페이지 소스 문서의 github 저장소
https://github.com/junhobaik/junhobaik.github.io/tree/develop

![junhobaik-homepage-source-github-repo]({{site.baseurl}}/img/junhobaik-homepage-source-github-repo.png)


## wonism

Gatsby로 만든 블로그형 홈페이지
https://wonism.github.io/

홈페이지의 github 리포지토리
https://github.com/wonism/wonism.github.io/tree/source

홈페이지 소스 문서의 github 저장소
https://github.com/wonism/wonism.github.io/tree/master




