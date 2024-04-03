# 202030215 서민석

# 4월 3일
## 1. Props 사용법
* JSX에서는 key-value쌍으로 Props를 구성함.
```js
function App(props) {
    return (
        <Profile
            name="소플"
            introduction="안녕하세요, 소플입니다."
            viewCount={1500}
            />
    );
}
```
* 위 코드는 Profile 컴포넌트로 name, introduction, viewCount Props를 전달한다.
* 이때 전달되는 props는 다음과 같은 자바스크립트 객체임.
```js
function App(props) {
    return (
        <Layout
            width={2560}
            height={1440}
            header={
                <Header title="소플의 블로그입니다." />
            }
        />
    );
}
```
* JSX에서는 중괄호를 사용하면 JS 코드를 넣을 수 있음.
* Props를 통해 value를 할당 할 수도 있고, 직접 중괄호를 사용하여 할당할 수도 있음.
***

```js
React.createElement(
    type,
    [props],
    [...children]
)
```
* JSX를 사용하지 않는 경우 props의 전달 방법은 createElement()함수를 사용해야 함
## 2. 컴포넌트 만들기
* 리액트 초기 버전을 사용할 때는 클래스형 컴포넌트를 주로 사용했음.
* 함수형 컴포넌트를 주로 사용함.
* 예전에 작성된 코드나 문서들이 클래스형 컴포넌트를 사용하고 있기에 클래스형 컴포넌트와 컴포넌트의 생명주기에 관해서도 공부해 두어야 함.
## 3. 컴포넌트의 종류
* 함수형 컴포넌트
    * Welcome컴포넌트는 props를 받아, 받은 props중 name키의 값을 "안녕,"뒤에 넣어 반환함.
* 클래스형 컴포넌트
    * Welcome컴포넌트는 React.Component class로부터 상속을 받아 선언함.
## 4. 컴포넌트 이름 짓기
* 이름은 항상 대문자로 시작해야함. 소문자로 시작하는 컴포넌트는 DOM 태그로 인식하기 때문.
* 컴포넌트 파일 이름과 컴포넌트 이름은 같게 해야 함.
## 5. 컴포넌트 렌더링
```js
function Welcome(props) {
    return <h1>안녕, {props.name}</h1>;
}

const element = <Welcome name="인제" />;
ReactDOM.render(
    element,
    document.getElementById('root')
);
```
* 기본적으로는 한 컴포넌트에 하나의 기능을 수행하도록 설계하는 것이 바람직함.
***
* 컴포넌트 합성
    * 컴포넌트 합성은 여러 개의 컴포넌트를 합쳐서 하나의 컴포넌트를 만드는 것
    * 리액트에서는 컴포넌트 안에 또 다른 컴포넌트를 사용할 수 있기 때문에, 복잡한 화면을 여러 개의 컴포넌트로 나누어 구현할 수 있음.
    * props의 값을 다르게 하여 컴포넌트를 여러번 사용함.
* 컴포넌트 추출
    * 복잡한 컴포넌트를 쪼개서 여러 개의 컴포넌트로 나눌 수 있음.
    * 큰 컴포넌트에서 일부를 추출하여 새로운 컴포넌트를 만드는 것
    * 실무에서는 처음부터 1개의 컴포넌트에 하나의 기능만 사용하도록 설계하는 것이 좋음.
## 6. State
```ruby
State는 리액트 컴포넌트의 상태를 의미함.
```
* State란?
    * 상태의 의미는 컴포넌트의 데이터(변경가능한 데이터)를 의미함.
    * State가 변하면 다시 렌더링이 되기 때문에 렌더링과 관련된 값만 state에 포함시켜야 함.
***
### State의 특징
* 리액트 만의 특별한 형태가 아닌 자바스크립트의 객체일 뿐임.
* state는 변경이 가능하다고 했지만 직접 수정해서는 안됨.(불가능하다고 생각하는 것이 좋음)
* state를 변경하고자 할 때는 setstate()함수를 사용

## 7. 생명주기란?
```ruby
생면주기는 컴포넌트의 생성 시점, 사용 시점, 종료 시점을 나타냄.
```
* 생명주기 특징
    * constructor가 실행되면서 컴포넌트가 생성됨.
    * 생성 직후 ComponentDidMount() 함수가 호출됨.
    * 컴포넌트가 소멸하기 전까지 여러번 렌더링 함.
    * 렌더링은 props, setState(), forceUpdate()에 의해 상태가 변경되면 이루어짐.
    * 렌더링이 끝나면 componentDinUpdate() 함수가 호출됨.
    * 컴포넌트가 언마운트 되면 componetWillUnmount()함수가 호출됨.
# 3월 27일
## 1. JSX (JavaScript Syntax eXtension) 란?
```ruby
JSX(JavaScript Syntax eXtension)는 JavaScript를 확장한 문법이다.
JSX는 리액트로 프로젝트를 개발할 때 사용되므로 공식적인 자바스크립트 문법은 아님.
브라우저에서 실행하기 전에 바벨을 사용하여 일반 자바스크립트 형태의 코드로 변환된다.
```
* JSX의 역할
    * JSX는 내부적으로 XML/HTML 코드를 자바스크립트로 변환함.
    * React가 createElement함수를 사용하여 자동으로 자바스크립트로 변환함.
    * 만일 js로 작업할 경우 직접 createElement함수를 사용해야 함.
    * 앞으로 설명하는 코드를 보면 알 수 있지만 결국 JSX는 가독성을 높여주는 역할을 한다.
```js
const name = '소플';
const element = <h1>안녕, {name}</h1>

ReactDOM.render(
    element,
    document.getElementById('root')
);
```
* 장점
    * 코드가 <span style="color:orange">간결</span>해 짐.
    * <span style="color:orange">가독성</span>이 향상 됨.
    * injection Attack이라 불리는 해킹 방법을 방어함으로써 보안에 강함.

* JSX 사용법
    * <span style="color:orange">모든 자바 스크립트 문법</span>을 지원함.
    * 자바스크립트 문법에 <span style="color:orange">XML과 HTML을 섞어서</span> 사용함.
    * 만일 HTML이나 XML에 자바스크립트 코드를 사용하고 싶으면 <span style="color:orange">{}괄호</span>를 사용함.
* Book.jsx
```js
import React from "react";

export default function Book(props) {
    return (
        <div>
            <h1>{`이 책의 이름은 ${props.name}입니다.`}</h1>
            <h2>{`이 책은 총 ${props.numOfPage}페이지로 이뤄져 있습니다.`}</h2>
        </div>
    );
}
```
* Library.jsx
```js
import React from "react";
import Book from "./book";

export default function Library() {
    return (
        <div>
            <Book name="처음 만난 파이썬" numOfPage={300} />
            <Book name="처음 만난 AWS" numOfPage={400} />
            <Book name="처음 만난 리액트" numOfPage={500} />
        </div>
    );
}
```
## 2. 엘리먼트에 대해 알아보기
* 엘리먼트의 정의
    * 엘리먼트는 리액트 앱을 구성하는 요소를 의미
    * 공식페이지에는 "엘리먼트는 리액트 앱의 가장 작은 빌딩 블록들"
    이라고 설명하고 있음.
    * 웹사이트의 경우는 DOM 엘리먼트이며 HTML요소를 의미

* 리액트 엘리먼트와 DOM 엘리먼트의 차이점
    * 리액트 엘리먼트는 Virtual DOM의 형태를 취하고 있음.
    * DOM 엘리먼트는 페이지의 모든 정보를 갖고 있어 무거움.
    * 반면 리액트 엘리먼트는 변화한 부분만 갖고 있어 가벼움.

||DOM|Virtual DOM|
|--|--|--
|업데이트속도|느리다|빠르다|
element 업데이트 방식|DOM 전체를 업데이트|변화 부분을 가상DOM으로 만든 후 DOM과 비교하여 다른 부분만 업데이트
메모리|낭비가 심함|효율적
* 엘리먼트의 생김새
    * 리액트 엘리먼트는 자바스크립트 객체의 형태로 존재
    * 컴포넌트(Button 등), 속성(color 등) 및 내부의 모든 children을 포함하는 일반 JS객체입니다.
    * 이 객체는 마음대로 변경할 수 없는 불변성을 갖고 있음.
```js
{
    type: 'button',
    props: {
        className: 'bg-green',
        Children: {
            type: 'b',
            props: {
                children: 'Hello, element!'
            }
        }
    }
}
```
    
```js
<button class='bg-green'>    
    <b>
        Hello,element!
    </b>
</button>
```
* 리액트 엘리먼트의 예를 보면 type에 태그 대신 리액트 컴포넌트가 들어가 있는 것 외에는 차이가 없다는 것을 알 수 있음.
```js
{
    type: Button,
    props: {
        color: 'green',
        children: 'Hello, element!'
    }
}
```
* 내부적으로 자바스크립트 객체를 만드는 역할을 하는 함수가 createElement임.
    * 첫 번째 매개변수는 type이고 이 곳에 태그가 들어가면 그대로 표현하고, 만일 리액트 컴포넌트가 들어가면 이 것을 분해해 결국 태그로 만들게 됨.
    * 두 번째 매개변수인 props는 속성을 나타냄.
    * 세 번째 매개변수는 children이며 자식태그라고 이해하면 됨.
```js
React.createElement(
    type,
    [props],
    [...children]
)
```
* 실제 CreateElement() 함수가 동작하는 과정


## 3. 엘리먼트의 특징
* 특징
    * 리액트 엘리먼트의 가장 큰 특징은 불변성임.
    * 즉, 한 번 생성된 엘리먼트의 children이나 속성(attributes)을 바꿀 수 없음.

* 만일 내용이 바뀐다면?
    * 이 때는 컴포넌트를 통해 새로운 엘리먼트를 생성하면 됨.
    * 그 다음 이전 엘리먼트와 교체를 하는 방법으로 내용을 바꾸면 됨.
    * 이렇게 교체하는 작업을 하기 위해 Virtual DOM을 사용함.
## 4. 엘리먼트 렌더링하기
* Root DOM node
다음 html코드는 id값이 root인 div태그로 단순하지만 리액트에 필수로 들어가는 아주 중요한 코드임.
* 이 div태그 안에 리액트 엘리먼트가 렌더링 되며, 이 것을 Root DOM node라고 함.
```html
<div id="root"></div>
```
* 엘리먼트를 렌더링하기 위해서는 다음과 같은 코드가 필요함.
```js
01  const element = <h1>안녕, 리액트!</h1>;
02  React.render(element, document.getElementById('root'));
```
* 이때 render()함수를 사용하게 됨.
* 이 함수의 첫 번째 패러미터는 출력할 리액트 엘리먼트이고, 두 번째 패러미터는 출력할 타겟을 나타냄.
* 즉 리액트 렌더링의 과정은 Virtual DOM에서 실제 DOM으로 이동하는 과정이라고 할 수 있음.
## 5. 렌더링 된 엘리먼트 업데이트

```js
1   function tick() {
2    const element = (
3        <div>
4            <h1>안녕, 리액트!</h1>
5            <h2>현재 시간: {new Date().toLocaleTimeString()}</h2>
6        </div>
7    );
8
9    ReactDOM.render(element, document.getElementById('root'));
10  }
11  
12  setInterval(tick, 1000);
```

* 다음 코드는 tick() 함수를 정의하고 있음.
* 이 함수는 현재 시간을 포함한 element를 생성해서 root div에 렌더링을 해줌.
* 라인12를 보면 setInterval()함수를 이용하여 위에서 정의한 tick()를 1초에 한번씩 호출하고 있음.
* 결국 1초에 한번씩 element를 새로 만들고 교체하는 것임.
* 다음 코드를 실행하고, 크롬 개발자 도구에서 확인해 보면 시간 부분만 업데이트 되는 것을 확인 할 수 있음.
## 6. 컴포넌트와 Props
* 컴포넌트의 개념
    * 2장에서 설명한 바와 같이 리액트는 컴포넌트 기반의 구조를 갖음.
    * 컴포넌트 구조라는 것은 작은 컴포넌트가 모여 큰 컴포넌트를 구성하고, 다시 이런 컴포넌트들이 모여 전체 페이지를 구성하는 것을 의미함.
    * 컴포넌트는 자바스크립트 함수와 입력과 출력이 있다는 면에서 유사함.
    * 다만 입력은 Props가 담당하고 출력은 리액트 엘리먼트 형태로 출력됨.
    * 엘리먼트를 필요한만큼 만들어 사용한다는 면에서 객체 지향의 개념과 비슷함.
***
* Props의 개념
    * Props는 Prop(Property: 속성, 특성)의 준말임.
    * 이 Props가 바로 컴포넌트의 속성임.
    * 컴포넌트에 어떤 속성, Props를 넣느냐에 따라 속성이 다른 엘리먼트가 출력 됨.
    * Props는 컴포넌트에 전달 할 다양한 정보를 담고 있는 자바스크립트 객체임.
* Props의 특징
    * 읽기 전용이며 변경할 수 없음.
    * 속성이 다른 엘리먼트를 생성하려면 새로운 Props를 컴포넌트에 전달하면 됨.
## 7. Pure 함수 / Impure 함수
```js
// pure 함수
// input을 변경하지 않으며 같은 input에 대해서 항상 같은 output을 리턴
function sum(a, b) {
    return a + b;
}
```
```js
// impure 함수
// input을 변경함.
function withdraw(account, amount) {
    account.total -= amount;
}
```
* Pure함수는 인수로 받은 정보가 함수 내부에서도 변하지 않는 함수임.
* Impure함수는 인수로 받은 정보가 함수 내부에서 변하는 함수임.
* 모든 리액트 컴포넌트는 Props를 직접 바꿀 수 없고, 같은 Props에 대해서는 항상 같은 결과를 보여줌.
# 3월 20일
## 1. React
```ruby
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
## 1. 마크다운
* 마크다운 특징
    * 마크다운(markdown)은 일반 텍스트 기반의 경량 마크업 언어다.
    * 일반 텍스트로 서식이 있는 문서를 작성하는 데 사용되며, 일반 마크업 언어에 비해 문법이 쉽고 간단한 것이 특징이다.
    * HTML과 리치 텍스트(RTF) 등 서식 문서로 쉽게 변환되기 때문에 응용 소프트웨어와 함께 배포되는 README 파일이나 온라인 게시물 등에 많이 사용된다.
## 1-2. 마크다운의 장점 및 단점
* 장점
    * 사용법이 쉽다.
    * 간결하다.
    * 텍스트로 저장이 되기 때문에 용량이 적으며 검색이 쉽다.
    * 지원하는 프로그램이 많다.
* 단점
    * 표준이 없기에 툴에 따라 생성물이 다르다.
    * 모든 HTML의 마크업을 대신하지 못한다.

## 2. 마크다운 문법
### Header
# H1<br>
* H1 태그는 최상위 영역(가장 큰 제목)에 사용되는 제목이다.
## H2<br>
* H2 태그는 H1 다음으로 제목에 사용되는 제목이다.
### H3

#### H4
##### H5
###### H6
* H3는 H2보다 한단계 아래 수준의 제목 태그로 사용되며 이러한 방식으로 H6 태그까지 계속된다.
***
## 3. 강조
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
