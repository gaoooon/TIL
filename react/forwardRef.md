## forwardRef

forwardRef는 부모 컴포넌트에서 자식 컴포넌트에 있는 element의 DOM에 접근하려고 할때 사용할수 있다
<br>
원래는 props로 ref를 전달하지 못하지만 forwardRef로 ref를 전달할수 있다

### 사용방법

```tsx
// 부모 컴포난트

const ParentComponents = () => {
  const inputRef = useRef(null);

  const focus = () => inputRef.current.focus();

  return (
    <div>
      <ChildComponents ref={inputRef} />
      <button onClick={focus}>focus</button>
    </div>
  );
};

export default ParentComponents;
```

```tsx
// 자식 컴포넌트

const ChildComponents = (ref) => <input ref={ref} />;

export default forwardRef(ChildComponents);
```

이런식으로 forwardRef를 사용해서 부모 컴포넌트에서 focus 버튼을 눌렀을때 자식 컴포넌트에 있는 input이 focus 되는 기능을 만들었다
ㄴㄴㄴㄴ
