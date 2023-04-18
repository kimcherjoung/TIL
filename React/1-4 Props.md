# Props
> props는 properties를 줄인 표현으로 컴포넌트 속성을 설정할 때 사용하는 요소입니다.  
> props값은 해당 컴포넌트를 불러와 사용하는 부모 컴포넌트에서 사용할 수 있습니다.

```
import React from "react";

const MyComponent = (props) => {
  return <div>안녕하세요. 제 이름은 {props.name}입니다.</div>;
};

export default MyComponent;
```
> 자식 컴포넌트에서 name이란 props를 렌더링하고 props값은 컴포넌트 함수의 파라미터로 받아와서 사용할수 있게 해줍니다.

```import MyComponent from "./MyComponent";

const App = () => {
  return <MyComponent name="React" />;
};

export default App;
```
>부모 컴포넌트에서 props 값을 정해준 겄이다
## 1. props 기본값 설정: defaultProps
```import MyComponent from "./MyComponent";

const App = () => {
  return <MyComponent name="React" />;
};

export default App;
```
>이렇게 props값을 지정해 주지 않았을때 값이 뜨지 않는겄을 방지하기 위해서 
```import React from "react";

const MyComponent = (props) => {
  return <div>안녕하세요. 제 이름은 {props.name}입니다.</div>;
};

MyComponent.defaultProps = {
  name: "기본 이름",
};

export default MyComponent;
```
>이렇게 defaultProps 값을 주면 아무 props값이 없어도 기본값이 사용될수 있다.

## 2. 태그 사이의 내용을 보여 주는 children
>리엑트 컴포넌트를 사용할 때 컴포넌트 태그 사이의 내용을 보여 주는 props가 있는데 children을 사용하면 된다.
```import MyComponent from "./MyComponent";

const App = () => {
  return <MyComponent>React</MyComponent>;
};

export default App;
```
> 이렇게 부모컴포넌트의 태그 사이의 있는 값을
```
import React from "react";

const MyComponent = (props) => {
  return (
    <div>
      안녕하세요. 제 이름은 {props.name}입니다. <br />
      children 값은 {props.children} 입니다.
    </div>
  );
};

MyComponent.defaultProps = {
  name: "기본 이름",
};

export default MyComponent;
```
> 이렇게 하면 태그사이에 있던 "React"라는 값이 children을 이용해 가져올 수 있게 된다
