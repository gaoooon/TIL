## styled-components

#### 사용이유

- css 파일을 따로 만들 필요가 없다
- css가 전역으로 중첩되지 않는다

<hr>

```
yarn add styled-components
```

styled-components를 추가해준다

<br>

- 컴포넌트 선언

```jsx
const Circle = styled.div`
  width: 5rem;
  height: 5rem;
  background-color: "black";
  border-radius: 50%;
`;
```

styled 다음에 원하는 태그를 쓴다음 ``안에 css 코드를 쓰면 된다

<br>

- props 사용

```jsx
function App() {
  return <Circle color="red" size={10} />;
}

const Circle = styled.div`
  width: 5rem;
  height: 5rem;
  background-color: ${(props) => props.color || "black"};
  border-radius: 50%;
  ${(props) =>
    `
      width: ${props.size}rem;
      height: ${props.size}rem;
    `}
`;
```

props를 이용해 size와 color를 설정할수 있다
