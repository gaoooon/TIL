## `useRef`

### Ref는 reference를 줄인것이다 reference의 뜻은 참조이다 <br> 따라서 useRef의 기능은 특정 DOM을 참조할때 사용할 수 있다

- #### 사용방법

```jsx
import { useEffect, useRef } from "react"; // useRef를 사용하기 위해서는 import 해줘야 한다

const input = useRef();
useEffect(() => {
  input.current.focus();
}, []);

return <input ref={input} type="text" />; // 이런식으로 input 태그를 참조할수 있다

// 페이지가 시작하면 바로 input창에 글을 쓸수 있게 된다
```

- #### 변수 관리

```jsx
import { useRef } from "react";

const plus = useRef(0);
const onBtnClick = () => {
  ++plus.current;
  console.log(plus.current);
};

return <button onClick={onBtnClick}>click!</button>; // 버튼을 누르면 plus의 current의 값이 1씩 증가 한다

// useRef는 값이 변한다고 해서 다시 렌더링 되지는 않는다
// 일반 변수는 렌더링한다면 값이 초기화 되지만 useRef를 사용한다면 렌더링 되도 값이 초기화 되지 않는다
```
