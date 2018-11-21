---
layout: post
title: 마크다운 블로그에 수식 사용
date: 2018-11-15 15:10:00 +0900
author: 원성규
excerpt: 문서 작성 시스템을 갖추게 되었다.
categories: markdown
tags:
- markdown
- Jekyll
- mathjax
keywords:
---

### 문서 작성 시스템

드디어 원하던 문서 작성 시스템을 갖추게 되었다. 내가 기대했던 글쓰기 환경의 대략적인 특성은 다음과 같다.

- 문서의 특성을 나타내는 여러개의 태그로 그 문서가 자동으로 분류되어야 한다.
- 문서는 텍스트로 작성되어 미래의 언제나 해독되어야 한다.
- 어떠한 컴퓨팅 환경에서도 해당 문서를 읽을 수 있어야 한다.
- 문서는 수식을 아름답게 표현할 수 있어야 한다.
- 문서는 보통의 그림 파일을 가공되지 않은 형태로 문장 사이에 포함시킬 수 있어야 한다.
- 문서는 서식을 갖추어 구조가 한눈에 들어와야 한다.

여기까지 특징을 살펴보면 두 단어가 떠오른다. Tex 그리고 HTML. 그렇다. 우리 시대에 컴퓨터를 사용하는 글쓰기의 지향점이 바로 이들이었다. 그리고 내가 가지고 있는 생각도 이와 일치한다.

다만 아무렇게나 텍스트를 갈겨쓰고 문장과 문단의 구분이라는 생각없이 적당한 호흡 조절용 마침표만을 지키는 사람들이 아직 많이 있다. 하지만 위와 같은 글쓰기 환경에서는 글쓰기의 방법과 형식을 따라갈 수 밖에 없어서 부지불식간에 강제로 구조적으로 글을 쓸 수밖에 없어서 이제 글쓰기 시스템으 갖춘 나역시 형식을 갖추어 글쓰는 데에 익숙해질 것이다.

이미 10년 전에 블로그라는 신조어가 나타났고 나는 그것이 별도의 글쓰기 형식으로만 이해하고 있었다. 하지만 이후 10여년이 지난 지금 인터넷 상의 대부분의 정보는 블로그 또는 그와 유사한 형식의 글로 유통되고 있다. 파일의 전송 방식이 조금 다를지언정 사용프로그램의 도움말 시스템도 이와 유사한 형식에서 출발하여 이제는 정보성 개인 블로그와 상용프로그램의 웹도움말은 본질적인 차이를 보이지 않는다.

기술 정보의 유통의 일부를 보자면 종이책을 보고 공부한 학습 노트를 블로그에 정리하던 시절에서 이제는 공식 문서화되지 않은 기술 정보가 블로그에 쌓이고 그것을 정제하여 이북 또는 종이책으로 출판되는 시절이 되었다.

나는 문자와 숫자 정보를 읽고 쓰고 가공하고 전달하는 종류의 대부분의 응용프로그램이 약 30년간 윈도우 네이티브로 개발되고 유통된 것을 보아왔는데 이제는 그런 종류의 프로그램들이 잘 보이지 않는다. 대부분의 기능들은 지난 10여년간 웹환경에서 모두 처리할 수 있게 되었고 이런 환경은 프로그램이라 불리지 않고 서비스라 불린다. 이 서비스 환경에서 프로그램과 프로그램 도움말의 유통 과정은 예전과 같이 별도로 존재하는 것이 아니라 모두 단일 채널인 웹브라우저 위에서 이루어진다.

화면에 본질적인 정보를 뿌리면 어플리케이션이 되고 그것을 운용하기 위한 정보를 뿌리면 도움말이 되는 것이다. 그리고 이 도움말의 형식은 익히 알고 있는 기술 블로그의 형식과 다르지 않다.

### 지킬과 마크다운

이제 막 완성한 문서 작성 시스템의 두 기둥은 지킬과 마크다운으로 구성된다. 나는 나의 생각을 글로 옮길 때 마크다운을 사용하기로 하였다. 마크다운은 약 5년전에 처음 알게 되었는데 그보다 더 이전에 사용했던 웹메모장의 텍스트 버전이라고 생각되었기 때문에 HTML을 직접 작성하던 것보다 좀더 쓸만해졌다고 생각했었다. 리치텍스트 에디터를 사용하고 위지위그를 쓰더라도 텍스트 소스를 가지고 고품질의 렌더링된 문서를 보고자 하는 기대를 충족할 수는 없었기 때문이다.

지킬은 마크다운 문서를 HTML 문서로 변환해준다. 변환해 줄뿐만 아니라 문서 소스를 웹브라우저에 배치하여 하나의 컨텐츠를 제공하는어플리케이션 환경을 만들어준다. 결과적으로 지킬을 사용하여 나는 마크다운으로 작성된 다수의 문서를 개인 블로그로 변환할 수 있다. 그리고 이 블로그 시스템은 홈서버 또는 깃허브와 같은 웹저장소에 업로드하여 개인용 정보 일지로 사용하거나 공개 정보로 전환할 수도 있다. 특히 스마트폰이 보급된 현시점에서 나의 성과와 포트폴리오를 정리하고 남에게 보여주는 용도로 많이 활용되고 있다.

### 마크다운에서 수식

웹환경에서의 수식 작성은 수년전에 MathJax와 MathML에서 기술개발이 완료되었고 MathML은 웹표준 작업이 진행중이라고 한다. 두 기술 모두 Javascript로 작성된 수식 표현 기술이며 출판 시스템인 LaTex의 수식 입력 규칙과 거의 호환된다.

결과적으로 HTML로 변환후에 수식이 포함될 것이므로 완성된 마크다운 문서 시스템에서도 수식을 입력할 수 있어야 한다. 아래는 아인슈타인의 질량 에너지 등가 법칙이다.

$$ E=mc^2 $$

```mathjax
$$ E=mc^2 $$
```

### 머메이드 차트

머메이드를 쓸 수 있는 마크다운 에디터의 종류는 다음과 같다.
- [mermaidjs-mermaid-live-editor](https://github.com/mermaidjs/mermaid-live-editor)
- [Typora](https://typora.io/)
- [vscode](https://code.visualstudio.com/)

머메이드 차트를 HTML에 보이려면 아래의 `Javascript` 코드를 포함해야 한다.

```html
<head>
    <script src="https://unpkg.com/mermaid@8.0.0-rc.8/dist/mermaid.min.js"></script>
    <script>mermaid.initialize({startOnLoad: true, theme: 'forest'});</script>
</head>
```

머메이드 차트 요소 (그림)

<div class="mermaid">
graph LR;
    CSS --> HTML((HTML));
    Javascript --> HTML;

    Javascript --> MathJax;
    MathJax --> HTML;

    Javascript --> Plotly;
    Plotly --> HTML;

    Javascript --> D3;
    SVG --> D3;
    D3 --topojson--> HTML;

    D3 --> Mermaid;
    Mermaid --> HTML;
    Mermaid --> Markdown;

    subgraph Jekyll
    HTML --> Blog;
    Markdown --HTML--> Blog;
    end

    subgraph NodeJS
    Blog --> HomeServer;
    end

    subgraph Git
    Blog --> Github;
    end
</div>

머메이드 차트 요소 (코드)

```html
<div class="mermaid">
graph LR;
    CSS --> HTML((HTML));
    Javascript --> HTML;

    Javascript --> MathJax;
    MathJax --> HTML;

    Javascript --> Plotly;
    Plotly --> HTML;

    Javascript --> D3;
    SVG --> D3;
    D3 --topojson--> HTML;

    D3 --> Mermaid;
    Mermaid --> HTML;
    Mermaid --> Markdown;

    subgraph Jekyll
    HTML --> Blog;
    Markdown --HTML--> Blog;
    end

    subgraph NodeJS
    Blog --> HomeServer;
    end

    subgraph Git
    Blog --> Github;
    end
</div>
```

머메이트 코드는 마크다운과 HTML 사용법이 다르다. HTML에는 `class`를 부여한 `div` 요소로 포함시켜야 한고 마크다운에는 코드 스니펫으로 포함시켜야 한다. 지킬에서 마크다운을 변환할 때는 마크다운 내부에 HTML 코드를 직접 입력해주어야 한다.

머메이트 차트를 HTML에 보이려면 `div` 요소 블럭을 HTML에 넣어야 하고, 
```html
<div class="mermaid">
graph LR;
    CSS --> HTML((HTML));
    Javascript --> HTML;
</div>
```

마크다운에 보이려면 스니펫 기호를 포함한 `mermaid` 스니펫 블럭을 넣어야 한다.

```markdown
```mermaid
graph LR;
    CSS --> HTML((HTML));
    Javascript --> HTML;
``` (end mermaid)
```









