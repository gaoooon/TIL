## `props`

### `props`는 `properties`를 줄인 말이다 우리가 컴포넌트에 어떠한 값을 줘야할때 사용한다

- #### 사용방법

```jsx
function Example(props) {
  console.log(props.name); // 보낸 값을 받아서 사용한다
  console.log(props.age);
  return (
    <div>
      <h1>{props.name}</h1>
      <h2>{props.age}<h2>
    </div>
  );
}

function App() {
  return(
    <Example name ="gaon" age ="17"/> // 컴포넌트에 값을 보낸다
    );
}
```

- #### destructuring

```jsx
// destructuring 문법을 사용한 방법
function Example({name, age}) { // 각각의 값들이 변수에 저장 된다
  console.log(name); // 보낸 값을 받아서 사용한다
  console.log(age);
  return (
    <div>
      <h1>{name}</h1>
      <h2>{age}<h2>
    </div>
  );
}

function App() {
  return(
    <Example name ="gaon" age ="17"/> // 컴포넌트에 값을 보낸다
    );
}
```

- #### prop type

```jsx
// props로 받는 값의 type을 정할수 있다
// PropType을 사용할때는 improt 해줘야 한다
import PropType from "prop-types";

function Example({name, age = 19}) {
  // 만약 age의 값이 오지 않았다면 임의로 지정해줄 수 있다
  console.log(name);
  console.log(age);
  return (
    <div>
      <h1>{name}</h1>
      <h2>{age}<h2>
    </div>
  );
}

Example.propTypes = {
  name:  PropType.string.isRequired,
  // name의 값은 문자열만 허용되고 isRequired는 꼭 값을 지정해줘야 한다라는 뜻이다
  age: PropType.number.isRequired,
};

function App() {
  return(
    <Example name ="gaon" age ={17}/>
    );
}
```

- #### children prop

```jsx
// children prop은 엘리먼트의 자식 엘리먼트를 prop으로 받는 것이다
function Example({children}) {
  console.log(children);
  return (
    <div>
      <button>{children}</button>
    </div>
  );
}

function App() {
  return(
    // Example 엘리먼트의 자식 엘리먼트인 'test'를 컴포넌트의 prop으로 전달한다
    <Example>test<Example/>
    );
}
```
