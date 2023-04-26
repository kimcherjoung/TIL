# State
> 리엑트에서 state는 컴포넌트 내부에서 바뀔 수 있는 값을 의미합니다.
> props는 컴포넌트가 사용되는 과정에서 부모 컴포넌트가 설정하는 값이며, 컴포넌트 자신은 해당 props를 읽기 전용으로만 사용할 수 있습니다.<br>
> 따라서 props는 부모 컴포넌트에서 바꿔주어야 하지만 state는 바꿀수 있습니다.

## 배열 비구조화 할당
>원래는 함수형 컴포넌트에선느 state를 사용하지 못했지만 hook이란 것을 이용해 사용할수 있다(hook은 나중에 배운다).
>hooks를 사용하기전에 배열 비구조화 할당이란 것을 알아보겠나이다.
>객체 비구조화 할당과 비슷하고 배열 안에 들어 있는 값을 쉽게 추출할 수 있게 해준다

```
const array = [1,2];
const one = array[0];
const two = array[1];
```
>위 코드는 array안에 있는 값을 one과 two에 담아 주는 코드이다.
```
const array = [1,2];
const [one, two] = array;
```
>위 코드처럼 배열 비구조화 할당을 사용하면 더 간단해지고 useState 사용법을 쉽게 이해할 수 있다.
```
import { useState } from "react";
import reportWebVitals from "./reportWebVitals";

const Say = () => {
  const [message, setMessage] = useState("");
  const onClickEnter = () => setMessage("안녕하세요");
  const onClickLeave = () => setMessage("안녕히 가세요");

  return (
    <div>
      <button onClick={onClickEnter}>입장</button>
      <button onClick={onClickLeave}>퇴장</button>
      <h1>{message}</h1>
    </div>
  );
};

export default Say;
```
>위 코드에서 useState 함수의 인자에는 상태의 초깃값을 넣어주고 첫 번째 원소는 현재 상태이고 두 번째 원소는 세터함수라 해서 상태를 바꿔줄수 있다.
