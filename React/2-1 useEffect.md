# useEffect
>useEffect는 리엑트 컴포넌트가 렌더링될 때마다 특정 작업을 수행하도록 설정할 수 있는 Hook입니다
```javascript
import { useState, useEffect } from "react";

const Info = () => {
  const [name, setName] = useState("");
  const [nickname, setNickname] = useState("");
  useEffect(() => {
    console.log("렌더링이 완료딤");
    console.log({
      name,
      nickname,
    });
  });

  const onChangeName = (e) => {
    setName(e.target.value);
  };
  const onChangeNickname = (e) => {
    setNickname(e.target.value);
  };

  return (
    <div>
      <div>
        <input value={name} onChange={onChangeName} />
        <input value={nickname} onChange={onChangeNickname} />
      </div>
      <div>
        <div>
          <b>이름:</b> {name}
        </div>
        <div>
          <b>닉네임:</b> {nickname}
        </div>
      </div>
    </div>
  );
};

export default Info;
```
>결고를 보면 컴포넌트가 처음 나타났을때 '렌더링이 완료되었습니다'라는 문구가 두 번 출력이 되었습니다  
>따라서 useEffect는 개발 환경에서 컴포넌트가 화면에 나타날 때 두 번 호출이 된다는 걸 알수 있습니다.
>
## 마운트될 때만 실행하고 싶을 때
>useEffect에서 설정한 함수를 컴포넌트가 화면에 맨 처음 렌더링될 때만 실행하고, 업데이트될 때는 실행하지 않으려면 함수의 두 번째 파라미터로 비어 있는 배열을 넣어 주면 됩니다  
```javascript
  useEffect(() => {
    console.log("렌더링이 완료딤");
  }, []);
```
>이렇게 수정을 해주면 컴포넌트가 처음 나타날 때만 콘솔에 문구가 나타나고 더 이상 나타나지 않는다

## 특정 값이 업데이트될 때만 실행하고 싶을 때
> useEffect를 사용할 때, 특정 값이 변경될 때만 호출하고 싶을 경우도 있을때는 
> useEffect의 두 번째 파라미터로 전달되는 배열 안에 검사하고 싶은 값을 넣어 주면 됩니다.
```
  useEffect(() => {
    console.log(name);
  }, [name]);
```
>이러면 name의 값이 업데이트될때만 실행이 됩니다

## 뒷정리
>useEffect는 기본적으로 렌더링고 난 직후마다 실행되며, 두 번째 파라미터 배열에 뭘 넣느냐에 따라 실행되는 조건이 달라집니다  
>컴포넌트가 언마운트되기 전이나 업데이트되기 직전에 어떠한 작업을 수행하고 싶으면 useEffect에서 뒷정리(cleanup)함수를 반환해 주어야 합니다
```javascript
import { useState, useEffect } from "react";

const Info = () => {
  const [name, setName] = useState("");
  const [nickname, setNickname] = useState("");
  useEffect(() => {
    console.log("effect");
    console.log(name);
    return () => {
      console.log("cleanup");
      console.log(name);
    };
  }, [name]);

  const onChangeName = (e) => {
    setName(e.target.value);
  };
  const onChangeNickname = (e) => {
    setNickname(e.target.value);
  };

  return (
    <div>
      <div>
        <input value={name} onChange={onChangeName} />
        <input value={nickname} onChange={onChangeNickname} />
      </div>
      <div>
        <div>
          <b>이름:</b> {name}
        </div>
        <div>
          <b>닉네임:</b> {nickname}
        </div>
      </div>
    </div>
  );
};

export default Info;
```
>이렇게 useEffect부분을 바꾸고
```javascript
import { useState } from "react";
import Info from "./Info";

function App() {
  const [visible, setVisible] = useState(false);
  return (
    <div>
      <button
        onClick={() => {
          setVisible(!visible);
        }}
      >
        {visible ? "숨기기" : "보이기"}
      </button>
      <hr></hr>
      {visible && <Info></Info>}
    </div>
  );
}

export default App;
```
>App.js 도 바꾸어 줘보면 React.StricMode가 활성화되있어 보이기 버튼을 누르면 컴포넌트가 두 번 마운트되면서 effect,cleanup,effect가 출력이 된다  
>인풋안에 이름을 적고 콘솔을 보면 렌더링 될때마다 뒷정리 함수가 계속나타나는 것을 볼수 있다  
>그리고 뒷정리 함숙 호출될 땐느 업데이트되기 직전의 값을 보여 준다
