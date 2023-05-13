# useRef
>useRef Hook은 함수 컴포넌트에서 ref를 쉽게 사용하게 해줍니다  
>Average컴포넌트에서 useRef를 이용해 "등록" 버튼을 누르면 포커스가 인풋 쪽으로 넘어가도록 코드를 작성해 보겠습니다
```javascript
import { useState, useMemo, useCallback, useRef } from "react";

const getAverage = (numbers) => {
  console.log("평균값 계산 중...");
  if (numbers.length === 0) return 0;
  const sum = numbers.reduce((a, b) => a + b);
  return sum / numbers.length;
};

const Average = () => {
  const [list, setList] = useState([]);
  const [number, setNumber] = useState("");
  const inputE1 = useRef(null);

  const onChange = useCallback((e) => {
    setNumber(e.target.value);
  }, []); //컴포넌트가 처음 렌더링될 때만 함수 생성
  const onInsert = useCallback(
    (e) => {
      const nextList = list.concat(parseInt(number));
      setList(nextList);
      setNumber("");
      inputE1.current.focus();
    },
    [number, list]
  ); //number 혹은 list가 바뀌었을 때만 함수 생성

  const avg = useMemo(() => getAverage(list), [list]);

  return (
    <div>
      <input value={number} onChange={onChange}></input>
      <button onClick={onInsert}>등록</button>
      <ul>
        {list.map((value, index) => (
          <li key={index}>{value}</li>
        ))}
      </ul>
      <div>
        <b>평균값:</b> {avg}
      </div>
    </div>
  );
};

export default Average;
```
>useRef를 사용해 ref를 설정하면 useRef를 통해 만든 객체 안의 current 값이 실제 엘리먼트를 가리킵니다  
## 로컬 변수 사용하기
>로컬 변수란 렌더링과 상관없이 바뀔 수 있는 값을 의미합니다  
>추가로 컴포넌트 로컬 변수를 사용해야 할때 useRef를 활용할 수 있습니다  
