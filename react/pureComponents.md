## 컴포넌트 순수성 유지

react는 컴포넌트를 순수함수로 유지 하려고 한다 순수함수라는 것은 무엇일까

### 순수함수란

- 자신의 일에만 신경씁니다. 호출되기 전에 존재했던 객체나 변수를 변경하지 않습니다.
- 동일 입력, 동일 출력. 동일한 입력이 주어지면 항상 동일한 결과를 반환해야 합니다.

수학 공식을 예로 들자면 `y=2x` 라는 식이 있다

```
x=2 라면 항상 y=4이다
x=1 이라면 항상 y=2이다
```

위의 식을 JavaScript 함수로 만들면 다음과 같다:

```
function double(number) {
  return 2 * number;
}
```

number가 2라면 return 값은 항상 4입니다

React는 이 순수 함수 개념을 중심으로 설계되었다<br>
React는 작성하는 모든 컴포넌트가 순수 함수라고 가정한다<br>
즉, 작성한 React 구성 요소는 동일한 입력이 주어지면 항상 동일한 JSX를 반환해야한다

```tsx
function TanghuluRecipe({ water }) {
  return (
    <ol>
      <li>Prepare water {water}g</li>
      <li>Prepare {0.5 * water}g sugar</li>
      <li>Put water and sugar in a paper cup and microwave it.</li>
    </ol>
  );
}

export default function App() {
  return (
    <section>
      <h1>Tanghulu Recipe</h1>
      <h2>For two</h2>
      <Recipe water={200} />
      <h2>For a gathering</h2>
      <Recipe water={400} />
    </section>
  );
}
```

water={200}를 TanghuluRecipe에 전달하면 항상 `Prepare water 200g`이 포함된 JSX를 반환한다

water={400}를 TanghuluRecipe에 전달하면 항상 `Prepare water 400g`이 포함된 JSX를 반환한다

마치 수학공식 처럼

컴포넌트를 레시피라고 생각한다면 레시피를 따르고 요리과정에서 새로운 재료를 넣지 않으면 매번 같은 요리를 얻을 수 있다 그 요리는 컴포넌트가 렌더링에 반응하기위해 제공하는 JSX이다

### 부작용(side effects): 의도하지 않은 결과

React의 렌더링 프로세스는 항상 순수해야 한다 컴포넌트는 JSX만 반환해야 하며 렌더링 전에 존재했던 객체나 변수를 변경하면 안 된다

다음은 이 규칙을 어기는 컴포넌트이다

```tsx
let guest = 0;

function Cup() {
  guest = guest + 1;
  return <h2>Tea cup for guest #{guest}</h2>;
}

export default function TeaSet() {
  return (
    <>
      <Cup />
      <Cup />
      <Cup />
    </>
  );
}
```

렌더링 전에 존재했던 변수 guest를 가져와 사용하고 있다 <br>
이는 이 컴포넌트는 호출할 때마다 다른 JSX가 생성된다는 뜻이다<br>
다른 컴포넌트가 guest를 읽으면 렌더링된 시점에 따라 JSX도 다르게 생성된다<br>
예측할 수 없는 일이다

y = 2x 공식으로 돌아가보면, 이제 x = 2라고 해도 y = 4라고 믿을 수 없게된다

guest를 prop으로 전달함으로써 이 컴포넌트를 순수하게 만들수 있다

```tsx
function Cup({ guest }) {
  return <h2>Tea cup for guest #{guest}</h2>;
}

export default function TeaSet() {
  return (
    <>
      <Cup guest={1} />
      <Cup guest={2} />
      <Cup guest={3} />
    </>
  );
}
```

이제 컴포넌트가 반환하는 JSX는 guest prop에만 의존하므로 순수하다

### Local mutation: 컴포넌트의 작은 비밀

위의 예시에서 문제는 컴포넌트가 렌더링 하는 동안 기존애 있던 변수를 변경하는 것이 문제였다<br>
이를 좀 더 무섭게 들리게 하기 위해 `변이? 돌연변이?`라고 부르기도 한다<br>
순수함수는 함수 범위에 벗어난 변수나 함수 호출 전에 생성된 변수나 객체를 변경하지 않는다

그러나 렌더링하는동안 생성한 변수나 객체는 변경되어도 괜찮다 밑에 예시에서는 cups 배열을 생성하고 12개의 Cup을 배열에 push 한다

```tsx
function Cup({ guest }) {
  return <h2>Tea cup for guest #{guest}</h2>;
}

export default function TeaGathering() {
  let cups = [];
  for (let i = 1; i <= 12; i++) {
    cups.push(<Cup key={i} guest={i} />);
  }
  return cups;
}
```

cups 배열이 함수 외부에서 생성 되었다면 큰 문제가 된다. 왜냐하면 해당 배열로 푸시하여 기존 배열을 변경하게 되기때문이다

### 사이드 이펙트 or 부작용을 일으킬 수 있는 곳

함수형 프로그래밍은 순수성에 크게 의존하지만, 언젠가는 어디선가 무언가를 바꿔야 한다. 이것이 바로 프로그래밍의 핵심이다.

React에서 사이드 이펙트는 보통 이벤트 핸들러에 속한다. 이벤트 핸들러는 사용자가 어떤 동작을 수행할 때 React가 실행하는 함수이다. 이벤트 핸들러가 컴포넌트 내부에 정의되어 있긴 하지만 렌더링 중에는 실행되지 않는다 따라서 이벤트 핸들러는 순수할 필요가 없다.

### 정리 및 마무리

- 컴포넌트는 순수 해야 한다
- 렌더링은 언제든지 발생할 수 있으므로, 컴포넌트는 서로의 렌더링 순서에 의존해서는 안된다
- 컴포넌트가 렌더링에 사용하는 어떠한 입력값도 변이해서는 안 된다. 여기에는 props, state 및 context가 포함된다. 화면을 업데이트하려면 기존 객체를 변이하는 대신 “set” state를 사용해라
- 컴포넌트의 로직을 반환하는 JSX 안에 표현하기 위해 노력하세요. “무언가를 변경”해야 할 때는 보통 이벤트 핸들러에서 이 작업을 하면 좋다
- 순수 함수를 작성하는 데는 약간의 연습이 필요하지만, React 패러다임의 힘을 발휘할 수 있다
