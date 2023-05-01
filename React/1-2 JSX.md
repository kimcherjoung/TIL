# JSX
>JSX는 자바스크립트의 확장 문법이며 XML과 매우 비슷하게 생겼습니다.<br>
 이런 형식의 코드는 브라우저에서 실행되기 전에 코드가 번들링되는 과정에서 바벨을 사용하여 일반 자바스크립트형태의 코드로 변환됩니다.
 
 ## JSX특징
 - 보기 쉽고 익숙하다.
 > html도 사용하기에 자바스크립트로 일일이 요소들을 만들어야한다면 너무 불편해진다
 - 더욱 높은 활용도를 가지고 있다
 > 앞으로 만들 컴포넌트를 JSX안에서 사용할수 있다
 ```javascript
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();
```
> 위 코드를 보면 index에서 App 컴포넌트를 마치 html태그 쓰듯이 쉽게 사용할 수 있다.

## JSX 문법
### 1. 감싸인 요소로 사용해야한다
```javascript
import logo from "./logo.svg";
import "./App.css";

function App() {
  return (
    <h1></h1>
    <h2>React</h2>
  )
}

export default App;
```
> 이런식으로 return안에 아무태그로도 감싸지지 않으면 안된다.
```javascript
import logo from "./logo.svg";
import "./App.css";

function App() {
  return (
    <div>
      <h1></h1>
      <h2>React</h2>
    </div>
  );
}

export default App;
```
>이런식으로 여러개의 요소를 하나의 부모요소로 감싸주어야 한다.
### 2. 자바스크립트 표현
```javascript
import logo from "./logo.svg";
import "./App.css";

const name = "react";
function App() {
  return (
    <div>
      <h1>{name} hello</h1>
      <h2>jal jakdong hani?</h2>
    </div>
  );
}

export default App;
```
> 이렇게 JSX 내부에는 자바스크립트 표현식을 쓸 수 있게 됩니다.<br>
> JSX내부에서 자바스크립트 표현식을 사용하려면 내부에서 코드를 {}로 감싸주면 됩니다.
### 3. if 문 대신 조건부 연산자
```javascript
import logo from "./logo.svg";
import "./App.css";

const name = "react";
function App() {
  return (
    <div>
      {name === "React" ? (
        <h1>React임</h1>
      ) : (
        <h2>React가 아님</h2>
      )}
    </div>
  );
}

export default App;
```
>위 코드처럼 조건문이 필요할때 JSX 내부에는 if문을 사용할 수 없고 조건부 연산자(삼항 연산자)를 사용하거나
>JSX밖에서 if문을 사용해서 사전에 값을 설정해 가져오는 방법밖에 없다.
### 4. undefined를 렌더링하지 않기
```javascript
import logo from "./logo.svg";
import "./App.css";

function App() {
  const name = undefined;
  return name;
}

export default App;
```
>리엑트 컴포넌트에서는 위에 코드처럼 함수에서 undefined만 반환하여 렌더링 하는 상황을 만들면 안 됩니다.
```javascript
import logo from "./logo.svg";
import "./App.css";

function App() {
  const name = undefined;
  return name || "undefined 임";
}

export default App;
```
위에 코드처럼 or연산자를 이용해 해당 값이 undefined일 때 사용할 값을 지정할수 있습니다.
```javascript
import logo from "./logo.svg";
import "./App.css";


function App() {
  const name = undefined;
  return <div>
    {name}
  </div>;
}

export default App;
```
JSX내부에서 undefined를 렌더링하는 것은 괜찮습니다.
### 5. 인라인 스타일링
```javascript
import logo from "./logo.svg";
import "./App.css";


function App() {
  const name = '리엑트';
  const style = {
    backgroundColor: 'black',
    color: 'aqua',
    fontSize: '40px',
    fontWeight: 'bold',
    padding : 16px
  };
  return <div style={style}>
    {name}
  </div>;
}

export default App;
```
>리엑트에서 DOM요소에 스타일을 적용할 때는 문자열 형태가 아닌 객체 형태로 넣어 주어야 해서 스타일 이름중에서 background-color처럼 문자에 -문자가 포함되는 문자는 backgroundColor
>처럼 카멜표기법을 이용해야한다
### 6. class 대신 className
```javascript
import logo from "./logo.svg";
import "./App.css";

function App() {
  const name = "리엑트";
  return <div className="react">{name}</div>;
}

export default App;
```
>요소에 클래스를 설정하는 과정에서 class가 아닌 className을 이용해야 한다
### 7. 꼭 닫아야 하는 캐그
```javascript
import logo from "./logo.svg";
import "./App.css";

function App() {
  const name = "리엑트";
  return (
    <div className="react">
      {name}
    </div>
    <br>
    <input>
    )
  ;
}

export default App;
```
>위에코드에서처럼 html에서는 br이나 input같은 태그는 닫는 태그가 없어도 되었지만 JSX에서는 
```javascript
import logo from "./logo.svg";
import "./App.css";

function App() {
  const name = "리엑트";
  return (
    <div className="react">
      {name}
    <br></br>
    <input></input>
    <br />
    <input />
    </div>
    )
  ;
}

export default App;
```
>위 코드처럼 닫는 태그가 있다던가 아니면 <br /> 이렇게 /를 이용해서 요약해서 사용할수 있다.
### 8. 주석
JSX안에서 주석은 
```javascript
import logo from "./logo.svg";
import "./App.css";

function App() {
  const name = "리엑트";
  return (

    <div className="react">
      {name}
    {/* 주석은 js와는 다르게 {}를 사용해야한다 */}
    //이런거나
    /* 이런건 주석이 되지 못한다 */
    </div>
    );
}

export default App;
```
js와는 다르게 {}를 사용하고 해야한다.
