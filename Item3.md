[본 문서는 한빛미디어의 소플의 처음 만난 리액트 (저자 이인제)를 참고하여 정리된 문서입니다.]

# JSX란
JavaScript and XML 
```
const element = <h1>Hello, world!</h1>;
```
특징
리액트 프로겢긑 개발에 사용됨으로 공식적인 자바스크립트 문법 x
JSX 하나의 파일에 JS + HTML 을 동시에 작성할 수있다

# JSX의 역할
JSX 를 자바 스크립트 코드로 변환하는 역할을 하는 것이 
createElement() 함수

➕
JSX 문법으로 작성한 코드는 바벨을 통해서 자바스크립로 변환된다
바벨: 트랜스파일(transpile)하는 바벨(Babel) 라이브러리
JSX를 쓰고 있다고 생각하지만, 실제로는 함수를 호출하고 있는 것입니다
# JSX의 장점
1.코드가 간결해진다
2.가독성이 향상된다
3.injection Attack 해킹을방어한다
# JSX 사용법 
모든 자바스크립트 문법을 지원한다
자바스크립트 사용시 중괄로 묶어서 사용 하면 된다
chilederen을 정의 하려면 상위태그 하위태그를 감싸도록 하면 된다
➕
1.표기법
JSX에서는 변수 또는 함수를 선언할 때 그리고 HTML의 style 속성을 기술할 때 카멜(camel) 표기법을 사용합니다. 
3.부모 요소 반환
JSX에서 HTML 태그를 반환할 때는 반드시 HTML 태그를 묶어주는 단 하나의 부모 태그가 있어야 합니다.
부모 태그로는 꼭 특정한 HTML 태그를 사용해야 하는 것은 아닙니다. 아래와 같이 Fragment라고 불리는 빈 태그 모양을 사용할 수도 있습니다.
```
return (
  <>
    <h1>Hello, world!</h1>
    <p>My name is Apple.</p>
  </>
)
```
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
