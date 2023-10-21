## useEffect

useEffect는 컴포넌트가 렌더링 될때마다 특정 작업을 실행하는 Hook이다

```jsx
useEffect();
```

useEffect는 1개나 2개의 인자를 받는다

- 첫번째 인자로는 callback 함수를 받는다(callback 함수는 다른 함수에 인자로 전달되는 함수이다)
- 두번째 인자로는 의존성 배열을 받거나 인자를 넣지 않을 수도 있다

두번째 인자인 의존성 배열 안에 있는 item이 업데이트 된다면 callback 함수를 실행한다

### 사용 예

```jsx
const Counter = () => {
  const [count, setCount] = useState(1);

  const increaseCount = () => setCount((prev) => prev + 1);

  // A
  useEffect(() => {
    console.log("렌더링!");
  });

  // B
  useEffect(() => {
    console.log("렌더링!");
  }, []);

  // C
  useEffect(() => {
    console.log("렌더링!");
  }, [count]);

  return (
    <div>
      <p>{count}</p>
      <button onClick={increaseCount}>increase</button>
    </div>
  );
};
```

위의 코드 처럼 인자에 따라 3가지 경우로 사용할 수 있다

- A useEffect는 컴포넌트가 처음 마운팅 되고 컴포넌트가 리렌더링 될때만 함수를 실행한다
- B useEffect는 컴포넌트가 처음 마운팅 되렀을때만 함수를 실행한다
- C useEffect는 컴포넌트가 처음 마운팅 + count가 업데이트 되었때 함수를 실행 한다

### clean up

clean up 이란 다른 컴포넌트에서 언마운트 되었을때 기존에 실행 하고 있던 것들을 정리 해주는 걸 말한다

### 사용 예

```jsx
const Timer = () => {
  useEffect(() => {
    const timer = setInterval(() => {
      console.log("타이머 실행중..");
    }, 1000);

    return () => {
      clearInterval(timer);
    };
  }, []);

  return (
    <div>
      <p>timer start!</p>
    </div>
  );
};
```

useEffect에 return 을 사용해서 언마운트때 실행할 함수를 지정해 줄수 있다
