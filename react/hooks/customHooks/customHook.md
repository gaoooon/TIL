## custom hook(커스텀 훅)

`커스텀 훅이란`
<br>
상태 관련 로직을 재사용하기 위해 사용되는 특별한 함수라고 할수 있다

`사용 이유`
<br>

- 재사용할수 있어서 중복된 코드를 줄일 수 있다
<hr>

### useInput

```jsx
export function useInput(initialValue, submitAction) {
  const [inputValue, setInputValue] = useState(initialValue);

  const handleChange = (e) => {
    setInputValue(e.target.value);
  };

  const handleSubmit = () => {
    setInputValue("");
    submitAction(inputValue);
  };

  return [inputValue, handleChange, handleSubmit];
}
```

내가 만들어본 useInput이라는 커스텀 훅이다

초기값과 버튼을 눌렀을때 어떻게 할것인지에 대한 함수를 받는다

```jsx
const displayMessege = (messege) => {
  alert(messege);
};

function App() {
  const [inputValue, handleChange, handleSubmit] = useInput("", displayMessege);

  return (
    <div>
      <h1>useInput</h1>
      <input value={inputValue} onChange={handleChange} />
      <button onClick={handleSubmit}>확인</button>
    </div>
  );
}
```

이런 식으로 사용할수 있다
