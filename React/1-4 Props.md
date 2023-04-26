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
## 3.비구조화 할당 문법을 통해 props 내부 값 추출하기
```
import React from "react";

const MyComponent = (props) => {
  const { name, children } = props;
  return (
    <div>
      안녕하세요. 제 이름은 {name}입니다. <br />
      children 값은 {children} 입니다.
    </div>
  );
};

MyComponent.defaultProps = {
  name: "기본 이름",
};

export default MyComponent;
```
> 이렇게 코드를 이용해 값을 바로 가져올수 있게 됩니다.
```
import React from "react";

const MyComponent = ({ name, children }) => {
  return (
    <div>
      안녕하세요. 제 이름은 {name}입니다. <br />
      children 값은 {children} 입니다.
    </div>
  );
};

MyComponent.defaultProps = {
  name: "기본 이름",
};

export default MyComponent;
```
> 이렇게 바로 props를 사용하면 간편화 시킬수 있게됩니다.
## 4.propsTypes를 통한 props 검증
>컴포넌트의 필수 props를 지정하거나 props의 타입을 지정할 때는 propTypes를 사용합니다.<br>
>우선 코드 상단에 import로 prop-types를 불러와야 한다.
```
import React from "react";
import PropTypes from 'prop-types';
```
>이렇게 불러왓다면
```
import React from "react";
import PropTypes from 'prop-types';

const MyComponent = ({ name, children }) => {
  return (
    <div>
      안녕하세요. 제 이름은 {name}입니다. <br />
      children 값은 {children} 입니다.
    </div>
  );
};

MyComponent.defaultProps = {
  name: "기본 이름",
};

MyComponent.propTypes={
  name: PropTypes.string
}

export default MyComponent;
```
>이렇게 defaultProps를 지정해주는겄과 비슷하게 하면 name값은 무조건 문자열 형태로 전달해야 된다는 것을 의미합니다. 
```
import MyComponent from "./MyComponent";

const App = () => {
  return <MyComponent name={3}>React</MyComponent>;
};

export default App;
```
>만약 부모컴포넌트에서 props를 문자열이 아니 이렇게 정수형으로 주게되면 실행은 되지만 console창에 오류가 뜬다.
## 5.클래스형 컴포넌트에서 props 사용하기
>클래스형 컴포넌트에서 props를 사용할 때는 render 함수에서 this.props를 조회하면 된다.<br>
>그리고 defaultProps와 propsTypes는 똑같은 방법으로 설정할 수 있다
```

class MyComponent extends Component {
  render() {
    const {name,children} = this.props;
  return (
    <div>
      안녕하세요. 제 이름은 {name}입니다. <br />
      children 값은 {children} 입니다.
    </div>
  );
}
}

MyComponent.defaultProps = {
  name: "기본 이름",
};

MyComponent.propTypes={
  name: PropTypes.string
}

export default MyComponent;
```
>이렇게 render 함수에서 this.props를 조회하면 됩니다.
>그리고 defaultProps와 propTypes는 똑같은 방식으로 설정할 수 있습니다.
