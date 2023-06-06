Chapter13. 합성 & 상속
합성(Composition)
컴포넌트에서 다른 컴포넌트를 담기
상황 : 컴포넌트에 어떤 자식 엘리먼트가 들어올 지 미리 예상할 수 없는 경우로 
박스 역할을 하는 Siderbar, Dialog와 같은 컴포넌트가 있습니다

위와 같은 상황에 컴포넌트의 경우 'children prop'을 사용하여 자식 엘리먼트를 출력에 그대로 전달하는 것을 권장합니다
props.children
태그와 태그 사이의 모든 내용을 표시하기 위해 사용되는 특수한 props
자식 엘리먼트의 내용을 그대로 출력할 수 있는 특수한 prop 이다

```
const Category = (props) => {
  return <ul>{props.children}</ul>;
};
export default Category;
```
Cateogory 컴포넌트를 생성 props.childlren 사용

```
const App() => (
    <Category>
      <li>first</li>
      <li>Second</li>
      <li>Another</li>
     </Category>
);     
```
현재 3개의 태그를 Catory컴포넌트로 구성해 보았습니다
하지만 추가가 될수 있습니다 이런경우 props.childeren을 사용하여 태그사이의 모든 내용을 표시해 주면됩니다

특수화
때로는 어떤 컴포넌트의 “특수한 경우”인 컴포넌트를 고려해야 하는 경우가 있습니다. 예를 들어,
WelcomeDialog는 Dialog의 특수한 경우라고 할 수 있습니다.  
상속 
Facebook에서는 수천 개의 React 컴포넌트를 사용하지만, 컴포넌트를 상속 계층 구조로 작성을 권장할만한 사례를 아직 찾지 못했습니다.
Component 자체로 재사용 가능하기때문에 상속을 따로 권하지 않는다.
위 처럼 재사용이 필요한 Component 를 분리하고, 이를 import해서 사용하는 것이 편리하다고 한다.
만약 UI 가 아닌 기능을 재사용하고 싶다면, 별도의 javascript 모듈로 분리하여 import 한 후 사용하는 것이 좋다고 한다.
