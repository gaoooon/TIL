## Recoil

recoil은 react 전용 상태관리 라이브러리이다

장점

- 손쉬운 상태관리

<hr>

### atom

atom은 전역 상태를 정의하는데 사용되는 개념이다

```tsx
atom({ key: "", default: "" });
```

- key : atom은 고유한 key를 가져 atom을 정의하거나 수정할때 식별할수 있다
- default : atom의 초기값을 정의 할때 사용된다

#### 값을 가져오거나 수정하기

```tsx
// atom의 값만 가져올때 사용
const atom = useRecoilValue(정의된 아톰);

// atomdml 값을 수정할때만 사용
const setAtom = useSetRecoilState(정의된 아톰);

// 값을 가져오거나 수정 둘다 할때 사용
const [atom, setAtom] = useRecoilState(정의된 아톰);
```

괄호 안에는 정의해놓은 atom을 넣어주면 된다

<hr>

### selector

selector는 파생된 상태를 정의하는 데 사용되는 개념이다

```tsx
const mileState = atom({
  key: "mileState",
  default: 0,
});

const kilometerState = selector({
  key: "kilometerState",
  get: ({ get }) => {
    const mile = get(mileState);
    return mile * 1.609;
  },
});
```

이런식으로 mileState에서 파생된 kilometerState를 정의했다

하지만 이렇게 한다면 읽기만 가능하고 쓸수는 없다

### 쓰기 가능한 selector

```tsx
const kilometerState = selector({
  key: "kilometerState",
  get: ({ get }) => {
    const mile = get(mileState);
    return mile * 1.609;
  },
  set: ({ set }, number) => {
    set(mileState, number / 1.609);
  },
});
```

set을 활용해 milestate을 업데이트 할수 있다
