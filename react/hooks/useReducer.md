## useReducer

useReducer는 React에서 상태 관리를 위해 제공되는 Hook 중 하나로 useState로 상태를 관리하기 복잡할때 사용한다

<hr>

```jsx
const [state, dispatch] = useReducer(reducer, initialState);
```

- state는 현재 값을 저장한다
- dispatch를 사용해 state의 상태를 변경한다
- reducer자리에 어떻게 상태를 변경할 것인지에 대한 함수를 받는다
- initialState 자리에 state의 초기값을 받는다

<hr>

```jsx
const ACTION_TYPE = {
  deposit: "예금",
  withdraw: "출금",
};

const reducer = (state, action) => {
  switch (action.type) {
    case ACTION_TYPE.deposit:
      return state + action.payload;

    case ACTION_TYPE.withdraw:
      return state - action.payload;

    default:
      return state;
  }
};

function AppBank() {
  const [number, setNumber] = useState(0);
  const [money, dispatch] = useReducer(reducer, 0);

  return (
    <div>
      <h2>useReducer 은행에 오신것을 환영합니다</h2>
      <p>잔고 : {money}원</p>
      <input
        type="number"
        value={number}
        onChange={(e) => {
          setNumber(parseInt(e.target.value));
        }}
        step={1000}
      />
      <button
        onClick={() => {
          dispatch({ type: ACTION_TYPE.deposit, payload: number });
        }}
      >
        예금
      </button>
      <button
        onClick={() => {
          dispatch({ type: ACTION_TYPE.withdraw, payload: number });
        }}
      >
        출금
      </button>
    </div>
  );
}
```

useReducer를 사용해 간단하게 만든 입출금 계산기(?)이다
<br>
예를 들어 input 값을 3000으로 하고 예금 버튼을 눌렀다고 가정해보자
<br>

->`예금 버튼을 누르면 dispatch를 실행하는데 인자로 type과 값을 보냈다`
<br>
->`reducer함수에서 state는 현재 상태인 0을 받고 action 객체인 { type: ACTION_TYPE.deposit, payload: number }을 받는다`
<br>
-> `type이 ACTION_TYPE.deposit이기 때문에 맞는 로직을 수행한다`
<br>
-> `return state + action.payload`
<br>
-> `money의 값이 3000으로 상태가 변경되었다`
