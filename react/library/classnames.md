## classnames 라이브러리

react에서 클래스 이름을 동적으로 넣어주고 싶을때 우리는 이런식으로 할수 있다

```jsx
function Button({ children, size, color }) {
  return <button className={`button ${size} ${color}`}>{children}</button>;
}
```

or

```jsx
function Button({ children, size, color }) {
  return (
    <button className={["Button", size, color].join(" ")}>{children}</button>
  );
}
```

하지만 classnames 라이브러리를 사용하면 더욱 간편하게 사용할 수 있다

<hr>

### 사용법

```
$ yarn add classnames
```

```jsx
import classNames from "classnames";
```

사용할떄는 import 해줘야 한다

```jsx
function Button({ children, size, color }) {
  return (
    <button className={classNames("button", size, color)}>{children}</button>
  );
}
```

classNames 괄호 안에 넣고 싶은 클래스 이름을 넣어 주고 사용하면 된다

```jsx
function Button({ children, isDark }) {
  return (
    <button className={classNames("button", isDark ? "balck" : "white")}>
      {children}
    </button>
  );
}
```

삼항연산자를 사용하는 방법도 있다
