## Redux-Toolkit

### 상태 관리 라이브러리란?

상태 관리 라이브러리는

<hr>

리덕스 툴킷은 기존 리덕스에서 있던 문제인 <b>스토어 구성이 복잡, 유용한 작업을 수행하려면 많은 패키지를 추가, 너무 많은 상용구 코드 필요</b> 등의 이유로 인해 더 사용하기 편하게 만든것이다

- ### Provider

  > 전역적으로 사용할수 있게 한다

- ### configureStore

  > store를 만들수 있게 한다

- ### createSlice

  > slice를 만들수 있게 한다

  > <b>\*slice</b>는 상태(state)와 상태를 업데이트하는 리듀서(reducer) 및 액션(action)을 묶어 놓은 것이다

- ### useSelector

  > reducer의 값을 가져올 수 있게 한다

- ### useDispatch
  > Slice안에 있는 함수를 실행할 수 있게 한다

<hr>

### 사용할때

### index.tsx

```tsx
import ReactDOM from "react-dom/client";
import App from "./App";
import { Provider } from "react-redux";
import store from "./store";

const root = ReactDOM.createRoot(
  document.getElementById("root") as HTMLElement
);
root.render(
  <Provider store={store}>
    <App />
  </Provider>
);
```

Provider로 App 컴포넌트를 감싸면 store 속성의 store 객체를 App컴포넌트 안에서
전역적으로 접근할 수 있게 해준다

<br>

### store/index.tsx

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

configureStore를 사용해 store를 만든다 객체를 인자로 받는다

객체 안에는 reducer 옵션을 넣을수 있는데 옵션 안에는 관리하고 싶은것을 넣으면 된다

<br>

### store/counterSlice.tsx

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

createSlice는 store에 reducer 옵션에 넣을 slice를 만드는 함수이다

객체 안에는 name(이름), initialState(초기값), reducers(값 업데이트 함수)를 넣어줄 수 있다

### App.tsx

```tsx
import { useDispatch, useSelector } from "react-redux";
import { increase, decrease } from "./store/counterSlice";

function App() {
  const dispatch = useDispatch();
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

useSelector를 사용해 값을 받아오고 있다 state는 store에 있는 상태값을 불러온다

counter는 상태값들중 하나이다

useDispatch는 슬라이스 안에 있는 reducer를 실행해 상태를 업데이트를 한다

dispatch괄호 안에 reducer를 넣으면 실행된다
