## Redux-Toolkit

리덕스 툴킷은 기존 리덕스에서 있던 문제인 <b>스토어 구성이 복잡, 유용한 작업을 수행하려면 많은 패키지를 추가, 너무 많은 상용구 코드 필요</b> 등의 이유로 인해 더 사용하기 편하게 만든것이다

- ### Provider

  > 전역적으로 사용할수 있게 한다

- ### configureStore

  > store를 만들수 있게 한다

- ### createSlice

  > slice를 만들수 있게 한다

- ### useSelector

  > reducer의 값을 가져올 수 있게 한다

- ### useDispatch
  > Slice안에 있는 함수를 실행할 수 있게 한다

<hr>

### index.tsx

```tsx
import { configureStore } from "@reduxjs/toolkit";
import counterSlice from "./counterSlice";

const store = configureStore({
  reducer: {
    counter: counterSlice.reducer,
  },
});

export default store;
```

### counterSlice.tsx

```tsx
import { createSlice } from "@reduxjs/toolkit";

const counterSlice = createSlice({
  name: "counter",
  initialState: 0,
  reducers: {
    increase(state) {
      return (state += 1);
    },

    decrease(state) {
      return (state -= 1);
    },
  },
});

export default counterSlice;
export const { increase, decrease } = counterSlice.actions;
```

### 사용할때

```tsx
import { useDispatch, useSelector } from "react-redux";
import { increase, decrease } from "./store/counterSlice";

function App() {
  const counterValue = useSelector((state) => state.counter);

  const increase = () => {
    dispatch(increase());
  };

  const decrease = () => {
    dispatch(decrease());
  };

  return (
    <div>
      <h1>{counterValue}</h1>
      <button onClick={increase}>+</button>
      <button onClick={decrease}>-</button>
    </div>
  );
}
```
