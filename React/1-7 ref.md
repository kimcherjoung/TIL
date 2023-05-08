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
````html
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
