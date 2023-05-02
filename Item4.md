# 엘리먼트의 정의
엘리먼트는 React 앱의 가장 작은 단위입니다.

브라우저 DOM 엘리먼트와 달리 React 엘리먼트는 일반 객체이며(plain object) 쉽게 생성할 수 있습니다. React DOM은 React 엘리먼트와 일치하도록 DOM을 업데이트합니다.

엘리먼트의 생김새
리액트 엘리면트는 자바스크립트 객체 형태로 존재
ex: 부변성
```
{
  type : 'button',
  props:{
    className: 'bg-green',
    children:{
      type: 'b',
      props:{
        children: 'Hello, element!'
         }
      }   
   }
}  
```

```
{
  type: Button,
  props: {
    color: 'green',
    children: 'Hello, element!'
    }
}    
```
```
React.createElement(
  type,
  [props],
  [...childeren]
)  
```
파라미터|HTML|리액트엘리먼트|
|------|:---:|:---:|
|첫번째 타입| 문자열 | 리액트 컴포넌트|
|두번째 props|attributes| attributes|
|세번째 chilren|하위 태그|자식 엘리먼트|

특징 
1 불변성
엘리먼트 생성후에 
Childeren이나 attributes를 바꿀수 없다

# 엘리먼트 렌더링하기
<img width="968" alt="스크린샷 2023-05-01 오후 11 26 50" src="https://user-images.githubusercontent.com/119731100/235675116-d6f7076b-ea92-45d8-b7d8-d123a26ccc12.png">



# 렌더링된 엘리먼트 업데이트하기

```
import React from "react";

function Clock(props) {
    return (
        <div>
            <h1>안녕, 리액트!</h1>
            <h2>현재 시간: {new Date().toLocaleTimeString()}</h2>
        </div>
    );
}

export default Clock;
```
Clock() 함수를 정의 
새로운 엘리멘트를 생성해서 바꾸는 것
