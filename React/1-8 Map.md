# Map
>웹애플리케이션을 만들다 보면 밑에처럼 반복되는 코드를 작성할 때가 있습니다.
```javascript
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
```javascript
arr.map(callback, [thisArg])
```
>위 함수의 파라미터는 밑에와 같습니다.
 - callback:새로운 배열의 요소를 생성하는 함수로 파라미터는 다음 3가지 입니다
  - currentValue: 현재 처리하고 있는 요소
  - index: 현재 처리하고 있는 요소의 index 값
  - array: 현재 처리하고 있는 원본 배열
 - thisArg(선택 항목): callback 함수 내부에서 사용할 this 레퍼런스

```javascript
var number = [1,2,3,4,5];

var processed = numbers.map(function(num){
  return num*num;
});

console.log(processed);
```
>이렇게 map함수를 이용해 배열 [1,2,3,4,5]의 각 요소를 제곱해서 새로운 배열을 생성했습니다.  
>결과로는 ``` [1,4,9,16,25] ``` 가 뜬다  
>위 코드를 ES6문법으로 바꿔쓰면
```javascript
const numbers = [1,2,3,4,5]
const result = numbers.map(num => num*num);
console.log(result);
```
>위에서 var를 const로 바꾸고 function부분을 화살표 함수를 사용하면 된다

## 데이터 배열을 컴포넌트 배열로 변환하기
```javascript
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

## KEY
>리엑트에서 key는 컴포넌트 배열을 렌더링했을 때 어떤 원소에 변동이 있었는지 알아내려고 사용합니다.  
>예를 들면 유동적인 데이터를 다룰때는 원솔ㄹ 새로 생성하거나 제거하거나 수정을 할수 있다

# Key 설정
>key 값을 설정할 때는 map함수의 인자로 전달되는 함수 내부에서 컴포넌트 props를설정하듯이 설정하면 된다.  
>key 값은 언제나 유일해야 하기에 데이터가 가진 고유값을 key값으로 설정해야 한다.
```javascript
const articleList = articles.map(article => (
  <Article
    title={article.title}
    writer={article.writer}
    key={article.id}
   />
));
```
>하지만 앞선 예제에선 이런 고유번호가 없기에 map 함수에 전달되는 콜백 함수의 인수인 index값을 사용하면 됩니다
```javascript
import React from "react";

const IterationSample = () => {
  const names = ["눈사람", "얼음", "눈", "바람"];
  const nameList = names.map((name, index) => <li key={index}>{name}</li>);
  return <ul>{nameList}</ul>;
};

export default IterationSample;
```
>이러면 더이상 개발자 도구에서 경고 메시지가 뜨지 않는다  
>고유한 값이 없을 때만 index값을 key로 사용해야 하는데 왜냐하면 index를 key로 사용하면 배열이 변경될 때 효율적으로 리렌더링을 하지 못하기 때문이다.

### filter
>이번 예시에선 배열에서 특정조건들만 분류할수 있는 filter함수를 사용하기에 알아두면 좋은 함수입니다.
```javascript
const numbers = [1,2,3,4,5,6];
const biggerThanThree = numbers.filter(number => number >3);
```
>을 하면 결과로는 ```[4,5,6]```이 나오게 됩니다
>또한 원하는 원소만 제외시킬 수도 있습니다.
```javascript
const numbers = [1,2,3,4,5,6];
const withoutThree = numbers.filter(number => number !== 3);
```
>이렇게 하면 3을 제외하고 ```[1,2,4,5,6]```만 남게 됩니다.

```javascript
import React, { useState } from "react";

const IterationSample = () => {
  const [names, setNames] = useState([
    { id: 1, text: "눈사람" },
    { id: 2, text: "얼음" },
    { id: 3, text: "눈" },
    { id: 4, text: "바람" },
  ]);
  const [inputText, setInputText] = useState("");
  const [nextId, setNextId] = useState(5);

  const onChange = (e) => setInputText(e.target.value);
  const onClick = () => {
    const nextNames = names.concat({
      id: nextId,
      text: inputText,
    });
    setNextId(nextId + 1);
    setNames(nextNames);
    setInputText("");
  };

  const onRemove = (id) => {
    const nextNames = names.filter((name) => name.id !== id);
    setNames(nextNames);
  };

  const namesList = names.map((name) => (
    <li key={name.id} onDoubleClick={() => onRemove(name.id)}>
      {name.text}
    </li>
  ));
  return (
    <>
      <input value={inputText} onChange={onChange}></input>
      <button onClick={onClick}>추가</button>
      <ul>{namesList}</ul>;
    </>
  );
};

export default IterationSample;
```
>위 코드에선 id값을 이용해서 id를 추가하거나 삭제하는 배열을 만들어 mao을 이용해 렌더링 한것이다.
>위에처럼 해서 이제 map의 key를 이용해 반복되는 데이터를 렌더링하는 법을 배웠다.
