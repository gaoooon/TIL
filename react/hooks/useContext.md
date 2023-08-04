## useContext

<img src="https://courses.cs.washington.edu/courses/cse190m/07sp/lectures/slides/images/dom_tree.gif">
<br>
이런 돔 트리가 있다고 해보자 body에 있는 정보를 li태그에 주려면 prop을 이용해 줄 수 있다
<br>
하지만 prop으로 주려면 ul태그를 거쳐서 줘야한다 지금이야 간단하지만 나중에 자식 컴포넌트가 더 많아 진다면 굉장히 비효율적이다
<br>
이럴때 사용할수 있는것이 useContext이다

<hr>

### context란?

react에서 context는 데이터를 컴포넌트간에 전역적으로 공유하는 방법을 제공하는 기능이다
<br>
특정 데이터를 prop으로 전달하지 않고도 하위 컴포넌트에 데이터를 전달할수 있는것이다

<hr>

### context 만들기

```jsx
import { createContext } = from "react";

export const TestContext = createContext(null);
```

context를 만들기 위해서는 createContext를 import 해줘야 한다
<br>
null 위치에는 null 대신에 다른 기본값을 넣어도 된다

<hr>

### context 사용하기

만든 context를 import 해주고 사용한다

```jsx
const App = () => {
  const [isDark, setIsDark] = useState(false);
  return (
    <TestContext.Provider value={(isDark, setIsDark)}>
      <Input></Input>
    </TestContext.Provider>
  );
};
```

context를 import 해주고 사용한다

```jsx
import { useContext } from "react";

const Input = () => {
  const { isDark } = useContext(TestContext);

  return (
    <div style={{ color: isDark ? "black" : "white" }}>
      <h1 style={{ color: isDark ? "white" : "black" }}>
        {isDark ? "color is black" : "color is white"}
      </h1>
      <input type="text" />;
    </div>
  );
};
```

useContext를 사용해 context를 가져와 사용할수 있다
