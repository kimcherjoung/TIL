# Event
>사용자가 브라우저에서 DOM요소들과 상호 작용하는 것을 이벤트라고 한다.

## 이벤트 사용할 때 주의 사항
1. 이벤트 이름은 카멜 표기법으로 작성한다
  - onclick -> onClick
  - onkeyunder -> onKeyUnder
2. 이벤트에 실행할 자바스크리브 코드를 전달하는게 아니라 함수 현태의 값을 전달한다.
  - Arrow function(화살표 함수)문법으로 함수를 만들어 전달하거나
  - 랜더링 부분 외부에 미리 만들어서 전달하는 법
3. DOM요소에만 이벤트를 설정할 수 있다
  - div,button,input,form,span등 DOM요소에는 이벤트를 설정할수 있지만 <MyComponenet />같은 만든 컴포넌트엔 이벤트를 자체적으로 설정할 수 없다.

## 이벤트 종류
1. Clipboard
2. Composition
3. Keyboard
4. Focus
5. Form
6. Mouse
7. Selection
8. Touch
9. UI
10. Wheel
11. Media
12. Image
13. Animation
14. Transition
>등이 있다

```
import { useState } from "react";

const EventPractice = () => {
  const [username, setUsername] = useState("");
  const [message, setMessage] = useState("");
  const onChangeUsername = (e) => setUsername(e.target.value);
  const onChangeMessage = (e) => setMessage(e.target.value);
  const onClick = () => {
    alert(username + ": " + message);
    setUsername("");
    setMessage("");
  };
  const onKeyPress = (e) => {
    if (e.key === "Enter") {
      onClick();
    }
  };
  return (
    <div>
      <h1>이벤트 연습</h1>
      <input
        type="text"
        name="username"
        placeholder="사용자명"
        value={username}
        onChange={onChangeUsername}
      />
      <input
        type="text"
        name="message"
        placeholder="아무거나 입력해 보세요"
        value={message}
        onChange={onChangeMessage}
        onKeyPress={onKeyPress}
      />
      <button onClick={onClick}>확인</button>
    </div>
  );
};

export default EventPractice;
```
위 코드에서 처럼 사용할수가 있습니다
 
