# 202030215 서민석

# 3월 20일
> ## 1. React
## 1-1. 리액트란?
```
웹 및 앱 유저 인터페이스를 위한 라이브러리
```
* 2023년 새롭게 오픈한 리액트의 공식 사이트 헤드 카피
    * 복잡한 사이트를 쉽고 빠르게 만들고, 관리하기 위해 만들어진 것이 바로 리액트이다.
    * 다른 표현으로는 SAP를 쉽고 빠르게 만들 수 있도록 해주는 도구라고 생각하면 된다.
## 1-2. 리액트의 장점
* 빠른 업데이트와 렌더링 속도
    * 이 것을 가능하게 하는 것이 바로 Virtual DOM이다.
    * DOM(Document Object Model)이란 XML, HTML 문서의 각 항목을 계층으로 표현하여<br> 생성, 변형, 삭제할 수 있도록 돕는 인터페이스이며, W3C의 표준이다.
    * Virtual DOM은 DOM 조작이 비효율적인 이유로 속도가 느리기 때문에 고안된 방법임.
    * DOM은 동기식, Virtual DOM은 비동기식으로 렌더링을 함.

* 컴포넌트 기반 구조
    * 리액트의 모든 페이지는 컴포넌트로 구성됨.
    * 하나의 컴포넌트는 다른 여러 개의 컴포넌트의 조합으로 구성할 수 있음.
    * 재사용성이 뛰어남
* 재사용성
    * 반복적인 작업을 줄여주기 때문에 생산성을 높여 줌
    * 또한 유지보수가 용이함.
    * 재사용이 가능하려면 해당 모듈의 의존성이 없어야 함.
* 모바일 앱 개발 가능
    * 리액트 네이티브라는 모바일 환경 UI프레임워크를 사용하면<br>크로스 플랫폼(Cross Platform) 모바일 앱 개발 가능
* 기타
    * 메타(구 페이스북)에서 오픈소스 프로젝트로 관리하고 있어 계속 발전하고 있음.
    * 활발한 지식 공유 & 커뮤니티

## 1-3. 리액트의 단점
* 방대한 학습량
    * 자바스크립트를 공부한 경우 빠르게 학습할 수 있음.
* 높은 상태 관리 복잡도
    * state, component life cycle 등의 개념이 있으나 그렇게 어렵진 않음.
# 3월 13일
> ## 1. 마크다운
마크다운(markdown)은 일반 텍스트 기반의 경량 마크업 언어다. 일반 텍스트로 서식이 있는 문서를 작성하는 데 사용되며, 일반 마크업 언어에 비해 문법이 쉽고 간단한 것이 특징이다. HTML과 리치 텍스트(RTF) 등 서식 문서로 쉽게 변환되기 때문에 응용 소프트웨어와 함께 배포되는 README 파일이나 온라인 게시물 등에 많이 사용된다.
## 1-2. 마크다운의 장점 및 단점
* 장점
    * 사용법이 쉽다.
    * 간결하다.
    * 텍스트로 저장이 되기 때문에 용량이 적으며 검색이 쉽다.
    * 지원하는 프로그램이 많다.
* 단점
    * 표준이 없기에 툴에 따라 생성물이 다르다.
    * 모든 HTML의 마크업을 대신하지 못한다.
***
> ## 2. 마크다운 문법
## 2-1. Header
# H1<br>
H1 태그는 최상위 영역(가장 큰 제목)에 사용되는 제목이다.
## H2<br>
H2 태그는 H1 다음으로 제목에 사용되는 제목이다.
### H3

#### H4
##### H5
###### H6
* H3는 H2보다 한단계 아래 수준의 제목 태그로 사용되며 이러한 방식으로 H6 태그까지 계속된다.
***
> ## 3. 강조
* *기울임*
```
*기울임*
```
* **굵게**(BOLD)
```
**굵게**
```
* ~~취소선~~
```
~~취소선~~
```
