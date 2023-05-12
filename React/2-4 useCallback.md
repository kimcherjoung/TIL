# useCallback
>useCallback은 useMemo와 상당히 비슷한 함수입니다. 주로 렌더링 성능을 최적화해야 하는 상황헤 사용을 하는데,  
>이 Hook을 사용하면 만들어 놨던 함수를 재사용할 수 있습니다
  
>전에 useMemo에서 구현한 Average컴포넌트를 보면 onChange와 Insert란 함수를 선언해 주었습니다  
>이렇게 선언하면
