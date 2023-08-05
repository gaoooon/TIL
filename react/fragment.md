## fragment

react에서는 컴포넌트를 return 할때 element들을 단하나의 최상위 태그로 감사써 return 해야 한다
<br>
그래서 대부분의 사람들은 div태그를 최상위 태그로 사용해 감싼다
<br>
이유 있이 div태그로 감싸는것은 상관이 없지만 이유 없이 div태그로 감싸면 비효율 적이다
<br>
이럴때 사용할수 있는 것이 fragment이다

장점

- Fragment는 불필요한 DOM node의 생성을 막기때문에 메모리를 적게사용한다

<hr>

### 사용방법

div 태그 대신에 `<Fragment> </Fragment>` or `<> </>` 감싸주면 된다

### 예시

```jsx
return (
  <>
    <Input />
    <Button />
    <CreateUser />
    <UserLIst />
  </>
);
```

이런식으로 사용된다
