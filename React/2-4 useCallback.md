# useCallback
>useCallback은 useMemo와 상당히 비슷한 함수입니다. 주로 렌더링 성능을 최적화해야 하는 상황헤 사용을 하는데,  
>이 Hook을 사용하면 만들어 놨던 함수를 재사용할 수 있습니다
  
>전에 useMemo에서 구현한 Average컴포넌트를 보면 onChange와 Insert란 함수를 선언해 주었습니다  
>이렇게 선언하면 컴포넌트가 리렌더링될 때마다 새로 만들어진 함수를 사용하게 되어 렌더링이 자주 발생하거나 개수가 많아지면 이 부분을 최적화 해주는 것이 좋습니다  
```javascript
import { useState, useMemo, useCallback } from "react";

const getAverage = (numbers) => {
  console.log("평균값 계산 중...");
  if (numbers.length === 0) return 0;
  const sum = numbers.reduce((a, b) => a + b);
  return sum / numbers.length;
};

const Average = () => {
  const [list, setList] = useState([]);
  const [number, setNumber] = useState("");

  const onChange = useCallback((e) => {
    setNumber(e.target.value);
  }, []); //컴포넌트가 처음 렌더링될 때만 함수 생성
  const onInsert = useCallback(
    (e) => {
      const nextList = list.concat(parseInt(number));
      setList(nextList);
      setNumber("");
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
>위에선 useCallback을 최적화 해보았습니다  
>useCallback의 첫 번재 파라미터에선 생성하고 싶은 함수를 넣고 두 번째 파라미터에는 배열을 넣으면 됩니다  
>이 배열에는 어떤 값이 바뀌었을 때 함수를 새로 생성해야 하는지 명시해야 합니다  
  
>onChange처럼 비어 있는 배열을 넣으면 컴포넌트가 렌더링될 때 만들었던 함수를 계속해서 재사용하게 되며, onInsert처럼 배열안에 number,list를 넣게 되면 인풋 내용이 바뀌거나 새로운 항목이 추가될때 새로 만들어진 함수를 사용하게 됩니다
    
>함수 내부에서 상태값에 의존해야 하면 그 값을 반드시 두 번째 파라미터안에 포함시켜 줘야 합니다  
>예를 들어 onChange의 경은 기존의 값을 조회하지 않고 바로 설정만 해서 배열이 비어있어도 상관없지만, onInsert는 기존의 number와 list를 조회해서 nextList를 생성하기에 배열안에 number와 list를 꼭 넣어 주어야 합니다
