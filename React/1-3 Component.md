# Component
>리엑트에서 UI요소를 나눌때 사용하는 단위이다<br>
>한 화면을 구성하는 요소를 컴포넌트로 나눠서 사용할수 있다<br>
>컴포넌트는 함수 컴포넌트와 클래스형 컴포넌트로 나뉘어 진다

## 함수형 컴포넌트
```javascript
import logo from "./logo.svg";
import "./App.css";

function App() {
  const name = "리엑트";
  return (
    <div className="react">{name}</div>
    );
}

export default App;
```
>함수형 컴포넌트는 이런 형식이다
### 장점은
> 1. 클래스형 컴포넌트보다 선언하기가 훨씬 편하다
> 2. 클래스형 컴포넌트보다 메모리 자원도 덜 사용한다
> 3. state와 API의 사용이 불가능했다가 hook이란 기능을 이용해 둘다 사용할수 있게 되었다.

```javascript
import logo from "./logo.svg";
import "./App.css";

const App = () => {
  const name = "리엑트";
  return (
    <div className="react">{name}</div>
    );
}

export default App;
```

> 이렇게 화살표 함수(arrow function)선언으로 더 간단히 사용할 수 있다.

## 클래스형 컴포넌트
```javascript
import { Component } from "react";

class App extends Component {
  render() {
    const name="react";
    return <div className="react">{name}</div>;
  }
}

export default App;
```
> 클래스형 컴포넌트는 이런형식으로 <br>
> render 함수가 꼭 있어야하고 그 안에서 보여줄 JSX를 반환해줘야 한다.

### 장점은
state 기능 및 라이프 사이클 기능을 사용할수 있고 임의 메서드를 정의할 수 있다
