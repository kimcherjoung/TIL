# Map
>웹애플리케이션을 만들다 보면 밑에처럼 반복되는 코드를 작성할 때가 있습니다.
```
import React from 'react'

const IterationSample = () => {
  return (
    <ul>
        <li>사람</li>
        <li>동물</li>
        <li>곤충</li>
        <li>외계인??</li>
    </ul>
  )
}

export default IterationSample
```
>위 코드를 보면 ```<li>...</li>```이 형태가 반복되는 것을 볼 수 있습니다.  
>자바스크립트 배열 객체의 내장 함수인 map함수를 사용해 반복되는 컴포넌트를 렌더링할 수 있습니다.  
>map함수는 파라미터로 전달된 함수를 사용해 배열 내 각 요소를 원하는 규칙에 맞춰 변환해서 그 결과로 새로운 배열을 생성합니다.  

## 문법
```
arr.map(callback, [thisArg])
```
>위 함수의 파라미터는 밑에와 같습니다.
 - callback:새로운 배열의 요소를 생성하는 함수로 파라미터는 다음 3가지 입니다
  - currentValue: 현재 처리하고 있는 요소
  - index: 현재 처리하고 있는 요소의 index 값
  - array: 현재 처리하고 있는 원본 배열
 - thisArg(선택 항목): callback 함수 내부에서 사용할 this 레퍼런스

```
var number = [1,2,3,4,5];

var processed = numbers.map(function(num){
  return num*num;
});

console.log(processed);
```
>이렇게 map함수를 이용해 배열 [1,2,3,4,5]의 각 요소를 제곱해서 새로운 배열을 생성했습니다.  
>결과로는 ``` [1,4,9,16,25] ``` 가 뜬다  
>위 코드를 ES6문법으로 바꿔쓰면
```
const numbers = [1,2,3,4,5]
const result = numbers.map(num => num*num);
console.log(result);
```
>위에서 var를 const로 바꾸고 function부분을 화살표 함수를 사용하면 된다

## 데이터 배열을 컴포넌트 배열로 변환하기
```
import React from "react";

const IterationSample = () => {
  const names = ["눈사람", "얼음", "눈", "바람"];
  const nameList = names.map((name) => <li>{name}</li>);
  return <ul>{nameList}</ul>;
};

export default IterationSample;
```
>위와 같이 names에 있던 데이터들을 ```<li>...</li>``` JSX코드로 된 배열을 새로 생성한 후 nameList에 담았다  
>그리고 실행해보면 원하는데로 리스트로 순서대로 나오게 됩니다.  
>그러나 개발자도구를 열면 key가 없다는 경고 메시지를 볼 수 있게 됩니다.
