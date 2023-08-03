## useCallback

useCallback은 useMemo처럼 최적화 할떄 사용된다, 하지만 useMemo와 차이점이 있다

- useMemo는 함수가 리턴하는 값을 Memoization하고 재사용한다
- useCallback은 함수를 Memoization하고 재사용한다

<hr>

```jsx
const someFunction = useCallback(() => {
  console.log("useCallback");
  return;
}, []);
```

useCallback은 2개의 인자를 받는다

- 첫번째 인자로는 Memoization할 함수를 받는다
- 두번째 인자로는 의존성 배열을 받는다

<hr>

### 사용 예

```jsx
function App() {
  const [number, setNumber] = useState(0);
  const [toggle, setToggle] = useState(true);

  const someFunction = () => {
    console.log(`someFunc: number: ${number}`);
    return;
  };

  useEffect(() => {
    console.log("someFunction이 변경되었습니다");
  }, [someFunction]);

  return (
    <div className="App">
      <input
        type="number"
        value={number}
        onChange={(e) => {
          setNumber(e.target.value);
        }}
      />
      <button
        onClick={() => {
          setToggle(!toggle);
        }}
      >
        {toggle.toString()}
      </button>
      <br />
      <button onClick={someFunction}>Call someFunc</button>
    </div>
  );
}
```

useCallback을 사용하지 않은 예이다 이렇게 코드를 짠다면 toggle 버튼을 눌렀을때도 상태가 변경되어 컴포넌트가 재호출되어 useEffect가 실행된다

```jsx
const someFunction = useCallback(() => {
  console.log(`someFunc: number: ${number}`);
  return;
}, [number]);
```

useCallback을 사용한다면 input의 값이 바뀔때만 someFunction이 업데이트 되기때문에
useEffect가 정상적으로 작동한다
