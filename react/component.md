## `컴포넌트(Componet)`

### 컴포넌트는 리액트에서 앱을 이루는 최소한의 단위이다

### 컴포넌트 종류는 크게 함수형(function) 컴포넌트와 클래스형(class) 컴포넌트가 있다

```jsx
// 함수 첫글자는 대문자로 한다
function App() {
  return (
    // return 값을 html 코드로 한다
    <div>
      <h1>App</h1>hello, App
    </div>
  );
}
```

### 컴포넌트 사용 장점

- #### 반복적인 개발이 줄어든다
- #### 수정이 편하다
