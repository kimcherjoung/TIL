# useReducer
>useState보다 더 다양한 컴포넌트 상황에 따라 다양한 상태를 다른 값으로 업데이트해 주고 싶을 때 사용하는 Hook이다  
>리듀서는 현재 상태, 그리고 업데이트를 위해 필요한 정보를 담은 액션(action) 값을 전달받아 새로운 상태를 반환한느 함수입니다.  
>리듀서 함수에서 새로운 상태를 만들 때는 반드시 불변성을 지켜주어야 합니다  
```javascript
function reducer(state, action) {
  return { ... }; //불변성을 지키면서 업데이트한 새로운 상태를 반환합니다
}
```
>액션 값은 주로 다음과 같은 형태로 이루어져 있습니다
```javascript
{
  type: 'INCREMENT',
  // 다른 값들이 필요하다면 추가로 들어감
}
```
### 구성요소
1. Dispatch - state 업데이트를 위한 요구를 하는 역할
2. Action - dispatch의 요구내용
3. Reducer - dispatch의 action값을 받아 state를 업데이트 하는 역할

## 카운터 구현하기
```javascript
import { useReducer } from "react";

function reducer(state, action) {
  //action.type에 따라 다른 적업 수행
  switch (action.type) {
    case "INCREMENT":
      return { value: state.value + 1 };
    case "DECREMENT":
      return { value: state.value - 1 };
    default:
      //아무것도 해당되지 않을 때 기존 상태 반환
      return state;
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, { value: 0 });

  return (
    <div>
      <p>
        현재 카운터 값은 <b>{state.value}</b>입니다.
      </p>
      <button onClick={() => dispatch({ type: "INCREMENT" })}>+1</button>
      <button onClick={() => dispatch({ type: "DECREMENT" })}>-1</button>
    </div>
  );
}

export default Counter;
```
>useReducer의 첫 번째 파라미터네는 리듀서 함수를 넣고, 두 번째 파라미터에는 해당 리듀서의 기본값을 넣어 준다.  
>이 Hook을 사용하면 state 값과 dispatch 함수를 받아 오는데, 여기서 state는 현재 가리키고 있는 상태고, dispatch는 액션을 발생시킨는 함수입니다.  
>dispatch(action)과 같은 형태로, 함수 안에 파라미터로 액션 값을 넣어 주면 리듀서 함수가 호출되는 구조입니다.

## 인풋 상태 관리하기
```javascript
import { useReducer } from "react";

function reducer(state, action) {
  return {
    ...state,
    [action.name]: action.value,
  };
}

const Info = () => {
  const [state, dispatch] = useReducer(reducer, {
    name: "",
    nickname: "",
  });
  const { name, nickname } = state;
  const onChange = (e) => {
    dispatch(e.target);
  };
  return (
    <div>
      <div>
        <input value={name} onChange={onChange} />
        <input value={nickname} onChange={onChange} />
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
>useReducer에서의 액션은 그 어떤 값도 사용이 가능합니다  
>그래서 이번엔 이벤트 객체가 지니고 있는 e.target 값 자체를 액션 값으로 사용했습니다  
>이런 식으로 인풋을 관리하면 인풋의 개수가 많아도 코드를 짧고 깔끔하게 유지할 수 
