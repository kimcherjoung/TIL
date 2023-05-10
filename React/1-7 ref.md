# ref
>일반 Html에서는 DOM 요소에 이름을 달 때는 id를 사용합니다  
>이렇게 DOM요소에 id를 달면 CSS나 자바스크립트에서 해당 id를 가진 요소를 찾아서 작업을 할수가 있습니다  
>이렇게 Html에서 id를 사용해 DOM에 이름을 다는 것처럼 리액트 내부에도 DOM에 이름을 다는 방법이 있는데 바로 ref(reference) 개념입니다

## ref를 사용해야 하는 상황
1. 페이지가 리렌더링 되어도 값(변수)를 유지시키고 싶을 때
>ref값은 state처럼 화면이 렌더링이 되면 초기화 되지 않는다
2. DOM을 꼭 직접적으로 건드려야 할 때
 - 포커스, 텍스트 선택영역, 혹은 미디어의 재생을 관리할 때.
 - 애니메이션을 직접적으로 실행시킬 때.
 - 스크롤 박스를 조작해야 할 때
 - Canvas 요소에 그림을 그려야 할 때 등
 - 서드 파티 DOM 라이브러리를 React와 같이 사용할 때

>예를 들어 일반 순수 자바스크립트와 jQuery로 만든 웹 사이트에서 input을 검증할 때는 다음과 같이 특정 id를 가진 input에 클래스를 설정해 줍니다.
```javascript
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>Example</title>
  <style>
    .success {
      background-color: lightgreen;
    }

    .failure {
      background-color: lightcoral;
    }
  </style>
  <script>
    function validate() {
      var input = document.getElementById('password');
      input.className='';
      if(input.value==='0000') {
        input.className='success';
      } else {
        input.className='failure';
      }
    }
  </script>
</head>
<body>
  <input type="password" id="password"></input>
  <button onclick="validate()">Validate</button>
</body>
</html>
```
>하지만 리엑트에서 이런 작업은 굳이 DOM에 접근하지 않아도 state로 구현할 수 있습니다
```javascript
import { Component } from "react";
import "./ValidationSample.css";

class ValidationSample extends Component {
  state = {
    password: "",
    clicked: false,
    validated: false,
  };

  handleChange = (e) => {
    this.setState({
      password: e.target.value,
    });
  };

  handleButtonClick = () => {
    this.setState({
      clicked: true,
      validated: this.state.password === "0000",
    });
  };

  render() {
    return (
      <div>
        <input
          type="password"
          value={this.state.password}
          onChange={this.handleChange}
          className={
            this.state.clicked
              ? this.state.validated
                ? "success"
                : "failure"
              : ""
          }
        ></input>
        <button onClick={this.handleButtonClick}>검증하기</button>
      </div>
    );
  }
}

export default ValidationSample;
```

>이렇게 state로 구현할 수 있지만 앞서 말했듯이 가끔 state만으로 해결할 수 없는 기능이 있어서 ref를 사용한다

## ref 사용
>이제 ref를 사용해볼건데 ref를 사용하는 방법은 두 가지입니다

## 콜백 함수를 통한 ref 설정
>ref를 만드는 가장 기본적인 방법은 콜백 함수를 사용하는 것입니다  
>ref를 달고자 하는 요소에 ref라는 콜백 함수를 props로 전달해 주면 됩니다  
```javascript
<input ref={(ref) => {this.input=ref}} />
```
>위의 콜백 함수는 ref값을 파라미터로 전달받고 함수 내부에서 파라미터로 받은 ref를 컴포넌트의 멤버 변수로 설정해 줍니다  
>이렇게 하면 앞으로 this.input은 input 요소의 DOM을 가리키게된다.  
>ref의 이름은 원하는 것으로 자유롭게 지정할수가 있다. DOM 타입과 관계없이 this.superman = ref처럼 맘대로 지정할 수 있다

## createRef를 통한 ref 설정
>ref를 만드는 또 다른 ㄹ방법은 리엑트에 내장되어 있는 createRef란 함수를 사용하는 것입니다  
>이 함수를 사용하면 더 적은 코드로 쉽게 사용할 수 있게 디고 , 이 기능은 리엑트 v16.3부터 도입되었으며 이전 버전에선 작동하지 않습니다
```javascript
import { Component } from 'react';

class RefSample extends Component {
 input = React.createRef();
 
 handleFocus = () => {
  this.input.current.focus();
 }
 
 render() {
  return (
   <div>
    <input ref={this.input}>
   <div>
  );
 }
}

export default RefSample;
```
>createRef를 사용하여 ref를 만들려면 우선 컴포넌트 내부에서 멤버 변수로 React.createRef()를 담아 주어야 합니다  
>그리고 해당 멤버 변수를 ref를 달고자 하는 요소에 ref props로 넣어 주면 ref 설정이 완료됩니다  
>설정한 뒤 나중에 ref를 설정해 준 DOM에 접근하려면 this.input.current를 조회하면 됩니다(콜백 함수와 다른 점은 뒷부분에 .current를 넣어 주어야 한드는 것이다)

## 커서 input으로 넘어가기 예제
>input에 커서가 있다가도 버튼을 누르면 input의 커서가 사라지므로 다시 input에 포커스가 다시 input 쪽으로 자동으로 넘어가도록 코드를 작성해 보겠습니다  
>콜백 함수를 이용해 ValidationSample 컴포넌트에도 ref를 달아보겠습니다
```javascript
        <input
          ref={(ref) => (this.input = ref)}
          (...)
         />
```
>콜백 함수를 이용해 여기에도  ref를 달아보았습니다
```javascript
   handleButtonClick = () => {
    this.setState({
      clicked: true,
      validated: this.state.password === "0000",
    });
    this.input.focus();
 };
 ```
>this.input이 input을 가리키고 있으니, 일방 DOM을 다루듯이 코드를 작성하면 됩니다
>이렇게 하면 input요소에 ref를 달아 직접 input을 가리키게 해서 focus를 주게 만들었습니다
 
## 컴포넌트에 ref 달기
>리엑트에선 컴포넌트에도 ref를 달 수 있습니다  
>이 방법은 주로 컴포넌트 내주에 있는 DOM을 컴포넌트 외부에서 사용할 때 씁니다. 컴포넌트에 ref를 다는 방법은 DOM에 ref를 다는 방법과 같습니다.
 
## 사용법
```javascript
<>
```
