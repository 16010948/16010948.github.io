---
title: "Nest.js"
categories:
  - BE
tags:
  - BE
  - Node
  - Nest.js
  - Express.js
last_modified_at: 2024-02-02T00:00:00-00:00
---

# ExpressJS

> 웹 및 모바일 애플리케이션을 위한 일련의 강력한 기능을 제공하는 간결하고 유연한 Node.js 웹 애플리케이션 프레임워크
> Node.js의 원칙과 방법을 이용하여 웹 애플리케이션을 만들기 위한 프레임워크

### 특징

- Typescript를 사용할 수 있지만, 설정 파일을 만들고 세팅하는 과정이 복잡
- 웹서버를 빠르게 구현하기 위해 개발시에 구조에 대한 자유도가 높음

# NestJS

> 효율적이고 확장 가능한 Node,js 서버측 애플리케이션을 구축하기 위한 프레임워크
> 프로그레시브 자바스크립트를 사용하고 Typescript로 빌드되고 완벽하게 지원하며, OOP(객체 지향 프로그래밍 Object Oriented Programming), FP(함수형 프로그래밍 Functional Programming), FRP(함수형 반응형 프로그래밍 Functional Reactive Programming) 요소를 결합
> Express를 기본으로 채택하고 그 위에 여러 기능을 미리 구현해 놓은 것
>
> ※ 프로그래시브: 웹과 네이티브 앱의 이점을 모두 수용하고 표준 패턴을 사용해 개발
> ※ 네이티브 앱: Android 또는 iOS 같은 어떤 구체적인 플랫폼만을 위해 만들어진 응용 프로그램

### 특징

- TypeScript를 적극적으로 도입함으로서 서버 어플리케이션 개발 시 발생할 수 있는 오류들을 사전에 방지할 수 있도록 함
- TypeScript를 사용하여 DI(Dependency Injection), IoC(Inversion of Control), 모듈을 통한 구조화 등 기술 생산성이 높음
- 모듈로 감싸는 형태로 개발하기 때문에 모듈별로 테스트 코드를 쉽게 작성할 수 있도록 구현되어 있음(안정적)
- 모둘을 통해 확장이 용이하도록 설계, 모듈을 통해코드적으로, 논리적으로 구분
- 마이크로서비스 아키텍처 개발 스타일 제공
- Spring과 사용 경험이 유사하고 Spring보다 간단함
- 간편하게 Validation로직 작성 가능(파이프 pip 사용)

## 비교

NestJS는 아키텍처 정의도 프레임워크에서 정의하기 때문에 각 개발자들의 아키텍처가 통일되고 개발자들이 서로 작성한 코드의 구조 쉽게 파악 가능

###### 출처

[NestJS과 Express 개녕 & 비교 (차이점, 특징 등)](https://nanbuja.com/entry/NestJS%EA%B3%BC-Express%EC%9D%98-%EA%B0%9C%EB%85%90-%EB%B9%84%EA%B5%90-%EC%B0%A8%EC%9D%B4%EC%A0%90-%ED%8A%B9%EC%A7%95-%EB%93%B1)

[Vue.js 란?](https://seungwongo.medium.com/vue-js-%EB%9E%80-8f865b34e53d)

[네이티브 앱(Native App) vs 하이브리드 앱(Hybrid App) vs 프로그레시브 웹 앱(PWA) – 정의와 장단점](https://www.hanl.tech/blog/native-vs-hybrid-vs-pwa/)
