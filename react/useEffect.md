## `useEffect`

### useEffect는 처음 페이지가 렌더링 되고 나중에는 특정 조건아니면 아예 실행이 안되게 할수 있는 함수이다

- #### 사용방법

```jsx
import { useEffect, useState } from "react"; // useEffect를 사용하기 위해서는 import해줘야 한다

useEffect(() => {
  console.log("test"); //이렇게 배열 안에 아무것도 넣지 않으면 처음 페이지가 렌더링 될때만 실행 된다
}, []);
```

- #### 특정 조건 실행

```jsx
import { useEffect, useState } from "react";

const [test, setTest] = useState(0);
const clickTest = () => {
  setTest((current) => current + 1);
};

useEffect(() => {
  console.log("test");
}, [test]); // 배열 안에 있는 값이 바뀌면 함수 안의 코드가 실행 된다

return <button onClick={clickTest}>Click</button>; // 버튼을 누르면 test의 값이 바뀐다
```
