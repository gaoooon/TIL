## useMemo

함수형 컴포넌트에서는 렌더링 되면 변수들이 초기화되면서 렌더링 된다<br>
하지만 사용하지 않을때도 초기화되면 비효율적이다<br> 그래서 사용할때만 초기화 되게 만들수 있게 만든것이 useMemo이다

- useMemo의 Memo는 Memoization으로 동일한 계산을 반복해야 할때 이전에 계산한것을 메모리에 저장하고 사용할때 마다 꺼내서 쓰는 것이다

<hr>

```jsx
import React, { useMemo } from "react";

const test = useMemo(() => {
  return 10;
}, []);
```

useMemo는 두개의 인자를 받는다

- 첫번째 인자로는 Memoization해줄 값을 계산해서 return해줄 함수가 들어간다
- 두번째 인자는 의존성 배열이 들어간다 (배열 안에 있는 변수가 바뀌면 다시 업데이트 해서 Memoization한다)

<hr>

#### 사용 예

```jsx
const hardCalculate = (number) => {
  console.log("어려운 계산!");
  for (let i = 0; i < 999999999; i++) {}
  return number + 10000;
};

const easyCalculate = (number) => {
  console.log("짱쉬운 계산!");
  return number + 1;
};

function App() {
  const [hardNumber, setHardNumber] = useState(1);
  const [easyNumber, setEasyNumber] = useState(1);

  const hardSum = useMemo(() => {
    return hardCalculate(hardNumber);
  }, [hardNumber]);

  const easySum = easyCalculate(easyNumber);

  return (
    <div>
      <h3>어려운 계산기</h3>
      <input
        type="number"
        value={hardNumber}
        onChange={(e) => setHardNumber(parseInt(e.target.value))}
      />
      <span> + 10000 = {hardSum} </span>

      <h3>쉬운 계산기</h3>
      <input
        type="number"
        value={easyNumber}
        onChange={(e) => setEasyNumber(parseInt(e.target.value))}
      />
      <span> + 1 = {easySum} </span>
    </div>
  );
}
```

hardCalculate함수에는 999999999번 반복하는 반복문을 넣어 1초 정도 딜레이가 있다<br>
근데 쉬운계산기의 input 값을 바꿀때도 함수가 렌더링되어 hardCalculate함수가 실행되면 비효율 적일 것이다<br> 그래서 hardSum을 useMemo를 사용해 어려운 계산기의 input 값이 바뀔때만 초기화 되도록 했다

<hr>

```jsx
const Memo = () => {
  const [number, serNumber] = useState(0);
  const [iskorea, setIsKorea] = useState(true);

  const location = {
    country: isKorea ? "한국" : "일본",
  };

  useEffect(() => {
    console.log("useEffect 호출!");
  }, [location]);

  return (
    <div>
      <h2>하루에 몇끼 먹어요?</h2>
      <input
        type="number"
        value={number}
        onChange={(e) => serNumber(e.target.value)}
      />
      <hr />
      <h2>어느 나라에 있어요?</h2>
      <p>나라: {location.country}</p>
      <button
        onClick={() => {
          setIsKorea(!iskorea);
        }}
      >
        비행기 타자
      </button>
    </div>
  );
};
```

useEffect의 의존성 배열에 location을 넣었는데 number의 상태를 변경해도 useEffect가 실행된다 <br>
왜냐하면 js에서는 객체 타입은 값이 저장될때 주소 값으로 저장이된다<br>
코드를 보면 number의 상태가 바뀌면 컴포넌트가 다시호출 되면서 location이 값이 같더라로 값이 저장된 주소가 바뀐다 그래서 useEffect에서는 값이 바꿨다고 인식해 함수가 실행된다

```jsx
const location = useMemo(() => {
  return {
    country: iskorea ? "한국" : "외국",
  };
}, [iskorea]);
```

이런식으로 useMemo를 사용해 값을 필요할때만 초기화 해준다면 문제가 없을것이다
