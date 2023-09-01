## input value

#### react에서 input 값의 접근할때는 크게 2가지 방법이 있다

- useState를 사용하는 방법
- useRef를 사용하는 방법

<hr>

### useState를 사용하는 방법(Controlled Input)

```jsx
const [inputValue, setInputValue] = useState("");

return (
  <input
    type="text"
    value={inputValue}
    onChange={(e) => setInputValue(e.target.value)}
  />
);
```

이런식으로 useState를 사용해서 값에 접근하는 방법이 있다

<hr>

### useRef를 사용하는 방법 (Uncontrolled Input)

```jsx
const inputRef = useRef(null);

return <input type="text" ref={inputRef} />;
```

이런식으로 useRef로 input의 DOM에 접근해서 값에 접근하는 방법이 있다

<hr>

### 차이

- useState를 사용한다면 input에 값이 바뀔때 마다 setter함수가 실행되서 렌더링이 되지만, useRef는 렌더링 되지 않는다
