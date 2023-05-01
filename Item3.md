[본 문서는 한빛미디어의 소플의 처음 만난 리액트 (저자 이인제)를 참고하여 정리된 문서입니다.]
# 1. JSX란
JSX(JavaScript XML)는 JavaScript와 XML을 결합한 것으로, React에서 UI를 구성하는 데 사용됩니다. 
JSX를 사용하면 HTML과 유사한 문법으로 UI를 작성할 수 있기 때문에 코드가 간결해지고 가독성이 향상됩니다.
```
const element = <h1>Hello, world!</h1>;
```

# 2. JSX의 역할
JSX 코드는 `createElement() 함수`를 통해 자바스크립트 코드로 변환됩니다. 
JSX 코드를 자바스크립트로 변환하는 이유는 브라우저에서 실행되는 자바스크립트 코드로 변환하여 효율적으로 렌더링하기 위함입니다.
```
// JSX문법
const element = (
  <h1 className="greeting">
      Hello, world!
  </h1>
)  

const element = React.createElement(
      'h1',
      {className: 'greeting'},
      'Hello, world!;
      )
```
```
// createElement() 함수 호출의 결과
const elemnet = {
    type: 'h1',
    props: {
        className:'greeting',
        chlidren: 'Hello, world!'
   }
}   
```

바벨(Babel) 사용
JSX 코드를 자바스크립트 코드로 변환하는 과정에서 바벨(Babel)과 같은 도구를 사용합니다. 
바벨을 통해 JSX 코드는 자바스크립트 코드로 변환되어 브라우저에서 실행됩니다. 바벨은 트랜스파일(transpile)하는 라이브러리로서, JSX 코드를 변환하는 데 사용됩니다.

# 3. JSX의 장점
### 3-1.코드가 간결해진다
JSX를 사용하면 HTML과 유사한 문법으로 UI를 작성할 수 있기 때문에 코드가 간결해집니다. 
JSX를 사용하면 복잡한 UI를 선언적으로 작성할 수 있으며, 코드의 가독성과 유지보수성을 높일 수 있습니다.
```
JSX 사용
<div> Hello, {name}</div>

JSX 사용 안함
React.createElemet('div',null,`Hello, ${name}`);
```

## 3-2.injection Attack 해킹을방어한다
# 4. JSX 사용법 
### 4-1 모든 자바스크립트 문법을 지원한다
### 4-2 자바스크립트 사용시 중괄로 묶어서 사용 하면 된다
```
const name = {
    firstName: "유",
    lastName: "경호",
};

const element = <h1>성은 {name.firstName}이고,
이름은 {name.lastName} 입니다</h1>;
```
### 4-3 chilederen을 정의 하려면 상위태그 하위태그를 감싸도록 하면 된다
JSX에서 HTML 태그를 반환할 때는 반드시 HTML 태그를 묶어주는 단 하나의 부모 태그가 있어야 합니다. 
이 부모 태그는 특정한 HTML 태그를 사용하지 않아도 되며, Fragment라는 빈 태그 모양을 사용할 수 있습니다.
```
return (
  <>
    <h1>Hello, world!</h1>
    <p>My name is Apple.</p>
  </>
)
```
➕
1.표기법
JSX에서는 변수 또는 함수를 선언할 때 그리고 HTML의 style 속성을 기술할 때 카멜(camel) 표기법을 사용합니다. 

조건부 렌더링
JSX 내부에서는 삼항 연산자(ternary opeator)를 사용해야 합니다. if 문이나 for 문은 값으로 평가되는 표현식이 아니기 때문에 JSX 내부에서 사용할 수 없습니다.
```
const authenticated = true
return (
  <> 
  { authenticated ? 
      <h1>Hello, world!</h1> : 
      <h1>Hello, stranger!</h1>
  } 
  </>
  
  ```
)