# life_cycle
1. 모든 리엑트 컴포넌트엔 라이프사이클(수명 주기)가 존재한다  
2. 컴포넌트의 수명은 페이지에 렌더링되기 전인 준비 과정에서 시작해 페이지에서 사라질 때 끝난다
3. 리엑트 프로젝트를 하다보면 컴포넌트를 처음으로 렡더링 할때 어떤 작업을 하던가  
4. 컴포넌트를 업데이트하기 전후로 어떤 작업을 처리하거나 불필요한 업데이트를 방지해야 할 수도 있다.  
5. 이때 컴포넌트의 라이프사이클 메서드를 사용한다  
6. 참고로 라이프사이클 메서드는 클래스형 컴포넌트에서만 사용할수 있고 함수 컴포넌트는 HOOKS기능을 사용해 비슷한 작업을 처리할 수 있다.

## 라이프사이클 메서드
>라이프 사이클 메서드의 종류는 총 아홉가지이다.  
>Will 접두사가 붙은 에서드는 어떤 작업을 작동하기 <b>전</b>에 실행되는 메서드  
>Did 접두사가 붙은 메서드는 어떤 작업을 작동한 <b>후</b>에 실행되는 메서드  
> 이 메서드들은 컴포넌트 클래스에서 덮어 써 선언함으로써 사용할 수 있다  

## 라이프사이클은 세 가지 카테고리로 나눈다
### 마운트(Mount)
>DOM이 생성되고 웹 브라우저상에 나타난느 것을 마운트(Mount)라고 합니다.  
>마운트가 호출하는 메서드들 입니다.
1. constructor
> 컴포넌트를 새로 만들 때마다 호출되는 클래스 생성자 메서드입니다
2. getDerivedStateFromProps
> props에 있는 값을 state에 넣을 때 사용하는 메서드입니다.
3. render
> 우리가 준비한 UI를 렌더링하는 메서드입니다.
4. componentDidMount
> 컴포넌트가 웹 브라우저상에 나타난 후 호출하는 메서드입니다.

### 업데이트(Update)
>컴포넌트는 다음과 같은 경우에 업데이트를 합니다
1. props가 바뀔 때
2. state가 바뀔 때
3. 부모 컴포넌트가 리렌더링될 때
4. this.forceupdate로 강제로 렌더링을 트리거할 때
>업데이트가 호출하는 메서드들 입니다.
1. getDerivedStateFromProps
> 이 메서드는 마운트 과정에서도 호출되며, 업데이트가 시작하기 전에도 호출됩니다. props의 변화에 다라 state 값에도 변화를 주고 싶을 때 사용합니다
2. shouldComponentUpdate
> 컴포넌트가 리렌더링을 해야 할지 말아야 할지를 결정하는 메서드입니다  
> true또는 false 값을 반환해야 하며 true를 반환하면 다음 라이프 사이클 메서드를 계속 실행하고 false를 반환하면 작업을 중지합니다(리렌더링되지 않는다)  
> 만약 특정 함수에서 this.forceUpdate() 함수를 호출한다면 이 과정을 생략하고 바로 render 함수를 호출합니다.
3. render
> 컴포넌트를 리렌더링 합니다
4. getSnapshotBeforeUpdate
> 컴포넌트 변화를 DOM에 반영하기 바로 직전에 호출하는 메서드입니다.
5. componentDidUpdate
> 컴포넌트의 업데이트 작업이 끝난 후 호출하는 메서드입니다.

### 언마운트(UnMount)
>마운트의 반대과정, 즉 컴포넌트를 DOM에서 제거하는 것을 언마운트라고 합니다.
>언마운트가 호출하는 메서드 입니다.
1. componentWillUnmount
> 컴포넌트가 웹 브라우저상에서 사라지기 전에 호출하는 메서드입니다.

## 라이프사이클 메서드 살펴보기
### render()함수
render() { ... }
1. 컴포넌트 모양새를 정의한다. 그래서 컴포넌트에서 가장 중요한 메서드라고 할 수 있다.
2. 이 메서드 안에서 this.props와 this.state에 접근할 수 있고, 리엑트 요소를 반환한다.
3. 요소는 div같은 태그가 될 수도 있고 따로 선언한 컴포넌트가 될 수도 있다
4. 메서드 안에서는 이벤트 설정이 아닌 곳에서 setState를 사용하면 안되고 브라우저의 DOM에도 접근하면 안된다
5. DOM정보를 가져오거나 state에 변화를 줄 때는 componentDidMount에서 처리해야 합니다.

### constructor 메서드
constructor(props) { ... }
1. 이함수는 컴포넌트의 생성자 메서드로 컴포넌트로 만들 때 처음으로 실행됩니다.
2. 이 메서드에서는 초기 state를 정할 수 있다

### getDerivedStateFromProps 메서드
1. 이 메서드는 리엑트 v.16.3 이후에 새로 만든 라이프사이클 메서드이다
2. props로 받아 온 값을 state에 동기화시키는 용도로 사용하며, 컴포넌트가 마운트될 때와 업데이트 될 때 호출됩니다.
```javascript
static getDerivedStateFromProps(nextProps, prevState) {
  if(nextProps.value !== prevState.value){
    return{ value: nextProps.value};
  }
  return null;
}
```

### componentDidMount 메서드 
componentDidMount() { ... }
1. 이 메서드는 컴포넌트를 만들고, 첫 렌더링을 다 마친 후 실행합니다.
2. 이 안에서 다른 자바스크립트 라이브러리 또는 프레임워크의 함수를 호출하거나 이벤트 등록, setTimeout, setInterval, 네트워크 요청 같은 비동기 작업을 처리하면 된다.

### shouldComponentUpdate 메서드
shouldComponentUpdate(nextProps, nextState) { ... }
1. 이 메서드는 props 또는 state를 변경했을 때, 리렌더링을 시작할지 여부를 지정하는 메서드이다.
2. 이 메서드에선 반드시 true 값 또는 false 값을 반환해야 하고 컴포넌트를 만들때 따로 생성하지 않으면 기본적으로 true값을 반환하고 false 값을 반환하면 업데이트 과정은 여기서 중지된다.
3. 이 메서드 안에서 현재 props와 state는 this.props와 this.state로 접근하고, 새로 설정될 props또는 state는 nextProps와 nextState로 접근할 수 있다

### getSnapshotBeforeUpdate 메서드
1. 이 메서드는 리엑트 v.16.3 이후 만든 메서드이다
2. 이 메서드는 render에서 만들어진 결과물이 브라우저에 실제로 반영되기 직전에 호출된다
3. 이 메서드에서 반환하는 값은 componentDidUpdate에서 세 번째 파라미터인 snapshot 값을 전달받을 수 있는데, 주로 업데이트하기 직전의 값을 참고할 일이 있을 때 활용됩니다(예: 스크롤바 위치 유지)
```javascript
getSnapshotBeforeUpdate(prevProps, prevState) {
  if(prevState.array !== this.state.array) {
    const { scrollTop, scrollHeight } = this.list
    return { scrollTop, scrollHeight };
  }
}
```

### componentDidUpdate 메서드
componentDidUpdate(prevProps, prevState, snapshot) { ... }
1. 이 메서드는 리렌더링을 완료한 후 실행합니다(업데이트가 끝난 직후이므로, DOM 관련 처리를 해도 무방합니다.)
2. 여기선 prevProps 또는 prevState를 사용하여 컴포넌트가 이전에 가졌던 데이터에 접근할 수 있습니다.
3. getSnapshotBeforeUpdate에서 반환한 값이 있다면 여기서 snapshot 값을 전달받을 수 있습니다.

### componentWillUnmount 메서드
componentWillUnmount() { ... }
1. 이 메서드는 컴포넌트를 DOM에서 제거할 때 실행합니다
2. componentDidMount에서 등록한 이벤트,타이머,직접 생성한 DOM이 있다면 제거 작업을 해야 합니다.

### componentDidCatch 메서드
1. componentDidCatch 메서드는 리엑트 v16에서 새롭게 도입되었으며 컴포넌트 렌더링 도중에 에러가 발생했을 때 애플리케이션이 먹통이 되지 않고 오류 UI를 보여 줄 수 있게 해 줍니다
```javascript
componentDidCatch(error, info) {
  this.setState({
    error: true
  });
  console.log({ error, info});
}
```
>여기서 error 파라미터에 어떤 에러가 발생했는지 알려 주며, info 파라미터는 어디에 있는 코드에서 오류가 발생했는지에 대한 정보를 줍니다.  
>앞의 코드에서는 그저 console.log만 했지만 나중에 실제로 사용할 때 오류가 발생하면 서버 API를 호출하여 따로 수집할 수도 있습니다.  

