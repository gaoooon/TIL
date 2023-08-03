## react.memo

react 함수형 컴포넌트는 호출 되면 자식컴포넌트까지 같이 호출된다<br>
하지만 자식컴포넌트에 전달되는 props가 똑같아도 부모컴포넌트가 호출될때 항상 같이 호출되면 비효율적이다

- react.memo를 사용해 컴포넌트를 최적화 할수 있다

<hr>

```jsx
import React, { memo } from "react";

export default memo(App);
```

- App이라는 컴포넌트를 내보낼때 memo로 감싸서 사용한다

react.memo는 react에서 제공하는 고차 컴포넌트(Higher-Order Component)이다<br>
HOC는 컴포넌트를 인자로 받고 최적화된 컴포넌트를 반환해준다<br>
HOC는 반환해주기 전에 prop check를 해서 prop이 바뀐게 있다면 새로 렌더링하고 없다면 렌더링하지 않고 Memoization된 값을 재사용한다

<hr>

```jsx
import { useState } from "react";
import Child from "./Child";

function App() {
  const [parentAge, setParentAge] = useState(0);
  const [childAge, setChildAge] = useState(0);

  const incrementParentAge = () => {
    setParentAge(parentAge + 1);
  };

  const incrementChildAge = () => {
    setChildAge(childAge + 1);
  };

  console.log("부모 컴포넌트 렌더링");

  return (
    <div>
      <h1>부모</h1>
      <p>age: {parentAge}</p>
      <button onClick={incrementParentAge}>부모 나이 증가</button>
      <button onClick={incrementChildAge}>자식 나이 증가</button>

      <Child name="홍길동" age={childAge}></Child>
    </div>
  );
}

export default App;
```

```jsx
import { memo } from "react";

const Child = ({ name, age }) => {
  console.log("자식 컴포넌트 렌더링");

  return (
    <div style={{ border: "2px solid powderblue", padding: "10px" }}>
      <h3>자녀</h3>
      <p>name: {name}</p>
      <p>age: {age}</p>
    </div>
  );
};

export default memo(Child);
```

자식 컴포넌트를 내보낼때 react.memo를 사용해서 내보냈다<br>
이렇게 하지 않았다면 '부모 나이 증가'버튼을 눌렀을때 자식컴포넌트의 prop에 아무 변화가 없지만 다시 호출되어 비효율적이었을 것이다
