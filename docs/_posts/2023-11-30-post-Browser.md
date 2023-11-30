---
title: "Browser"
categories:
  - CS
tags:
  - CS
  - Browser
  - HTML
  - CSS
  - JavaScript
last_modified_at: 2023-11-30T00:00:00-00:00
---

# 브라우저 작동 원리

## 브라우저

> 웹 브라우저는 동기(Synchronous)적으로 HTML, CSS, JavaScript 언어를 해석하여 내용을 화면에 보여주는 응용 소프트웨어

※ 동기적인 이유

- DOM이 완성되기 전에 script가 DOM을 조작한다면 에러가 발생한다.
- 자바스크립트는 렌더링 엔진이 아닌 자바스크립트 엔진이 처리한다.

## 브라우저 구조

![웹 브라우저의 구조](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FRYadO%2Fbtrb82lgpwU%2F9nSSKSKfgpnwI2KKkxf4w1%2Fimg.png)

### 사용자 인터페이스(User Interface)

: 사용자가 접근할 수 있는 영역
요청한 페이지를 보여주는 창을 제외한 나머지 모든 부분

### 브라우저 엔진(Browser Engine)

: 사용자 인터페이스와 렌더링 엔진 사이의 동작을 제어하는 엔진
HTML문서와 기타 지원의 웹페이지를 사용자의 장치에 시각 표현으로 변환 시키며, 문서 객체 모델(DOM) 자료구조를 구현
레이아웃 엔진(Layout Engine)이라고도 불림
웹 브라우저마다 전용 엔진 사용

### 렌더링 엔진(Rendering Engine)

: HTML과 CSS, JavaScript를 파싱하고 그 결과물을 바탕으로 페이지를 그려내는 역할

- Gecko: Mozila 재단에서 만든 브라우저 엔진으로, 파이어폭스가 탑재하고 있음
- Webkit: KHTML에서 파생된 브라우저 엔진으로, 사파리가 탑재하고 있음
- Blink: 웹킷(Webkit)에서 파생된 브라우저 엔진으로, 크롬, 오페라가 탑재하고 있음
- Trident: 마이크로소프트의 브라우저 엔진으로, 아웃룩 익스프레스, 마이크로소프트 아웃룩 등이 탑재하고 있음

### 통신(Networking)

: HTTP나 HTTPS 같은 프로토콜을 이용해 외부의 리소스를 얻어오고, 서버에 요청을 보낼 때 사용되는 레이어

### 자바스크립트 해석기(JavaScript Interpreter)

: JavaScript 코드를 해석하고 실행하는 역할
JavaScript는 코드를 위에서부터 아래로 한 줄씩 읽어가는 방식으로 파싱(Parsing)하는 언어(Interpreted Language)이기 때문에 해석기가 필요
웹 브라우저마다 전용 자바스크립트 엔진이 탑재되어 있음

- Rhino: Mozila 재단이 운영하는 오픈 소스 엔진으로, Java로 개발됨
- Spider Monkey: 최초의 JavaScript 엔진으로 넷스케이프 내비게이터를 지원했으며 현재는 파이어폭스를 지원하고 있음
- V8: 구글이 개발한 오픈소스 엔진으로, 구글 크롬을 지원하고 있음
- JavaScriptCore: 애플에서 개발한 엔진으로 WebKit
- Chakra: 마이크로소프트가 개발한 엔진으로, Edge 브라우저를 지원하고 있음

### UI 백엔드

: 렌더링 엔진이 분석한 Render Tree를 브라우저에 그리는 역할
얼럿(Alert)나 셀렉트 박스(Select)가 운영체제 별로 다르게 동작

### 웹 스토리지(Web Storage)

: 쿠키나 로컬스토리지, 세션스토리지, IndexedDB 등의 브라우저 메모리를 활용하여 저장하는 영역

- 로컬 스토리지: 영구적인 저장
- 세션 스토리지: 임시적인 저장

#### 웹 스토리지 특징

- 웹 브라우저가 직접 데이터를 저장할 수 있게 해주어, 사용자 측에서 좀 더 많은 정보를 안전하게 저장할 수 있게 해준다.
  -> 이러한 정보는 서버로 전송되지 않고 클라이언트가 저장하고 있기 때문에 네트워크 트래픽 비용 또한 줄여준다.
- 웹 스토리지는 출처(origin)마다 단 하나씩 존재
  하나의 오리진에 속하는 모든 웹 페이지는 같은 데이터를 저장하기 때문에 같은 데이터에 접근할 수 있게 된다.
  ![브라우저 url 구조](https://velog.velcdn.com/images/wlwl99/post/0ef00474-bb9b-4603-8b63-40c79896bc59/image.png)

## 렌더링 엔진의 동작 과정

![렌더링 엔진 동작 과정](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FWbcmc%2Fbtrb2ccbSyK%2F2TYYpp5TvLFkdVbSYFIq3K%2Fimg.png)

- 파싱(Parsing)
- 렌더 트리(Render Tree) 구축
- 레이아웃(Layout) 또는 리플로우(Reflow)
- 페인트(Paint)

### 파싱

: 토큰화(Tokenize)된 코드를 구조화하는 과정

> 정확하게는 어휘분석기(Lexical scanner, Lexer)를 통해 토큰화된 코드가 생성되고, 이를 파서가 해석하는 순서로 이루어집니다. 토큰화라는 것은 의미가 있는 최소 단위로 코드를 쪼개는 것을 의미합니다.

#### HTML 파싱

브라우저는 HTML의 문자열들을 이용해 파스 트리(Parse Tree)를 생성합니다.

브라우저는 파스 트리를 이용해 **DOM(Document Object Model)** 트리를 새로 만들기 때문입니다.

파스 트리는 토큰화 된 문자열을 단순하게 구조화한 트리에 불과했지만, DOM 트리는 우리가 실제로 상호작용할 수 있는 HTML 엘리먼트로 이루어진 트리입니다. 따라서 우리가 실제로 JavaScript로 상호작용할 수 있는 부분은 DOM 트리입니다.

#### HTML 파서 특징

- 오류에 너그러운(forgiving nature) 속성
- 파싱 과정이 중단될 수 있음
  - HTML은 파싱 도중 `<script> `, `<link>` 같은 외부 태그를 만나게 되면 HTML 파싱을 즉시 중단하고 해당 태그의 해석을 실행
- 재시작(Reentrant)
  - 파싱 중간에 외부의 요인으로 인해 DOM이 추가, 변경, 삭제될 수 있는데 이러한 경우에 HTML은 처음부터 다시 파싱 과정을 거침
  - 바이트를 문자로 변환하고, 토큰을 식별한 후 노드로 변환하고 DOM 트리를 빌드

###### 출처

[[CS] 웹 브라우저는 어떻게 작동하는가?](https://bbangson.tistory.com/87)

[브라우저 동작 원리 & 구조](https://velog.io/@wlwl99/%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80-%EB%8F%99%EC%9E%91-%EC%9B%90%EB%A6%AC-%EA%B5%AC%EC%A1%B0)

[프론트엔드 개발자라면 알고 있어야 할 브라우저의 동작 과정](https://yozm.wishket.com/magazine/detail/1338/)
