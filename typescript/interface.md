## Interface

인터페이스는 객체나 함수등에 내용에 규칙을 정해 놨다고 생각하면 된다

<hr>

```tsx
// 객체
type Score = "A" | "B" | "C" | "F";

interface User {
  name: string;
  age: number;
  gender?: "F" | "M"; // ?를 붙이면 써도 되고 안써도 된다는 뜻이다
  readonly brithyear: number; // 앞에 readonly를 붙이면 읽기 전용으로 나중에 값을 바꿀수 없다
  [grade: number]: Score; // 대활호를 사용하면 여러개를 받을수 있다 여기에서는 number를 키로 받고 값은 Score중 하나로 사용가능하다
}

let user: User = {
  name: "kyumbi",
  age: 17,
  gender: "M",
  brithyear: 2007,
  1: "B",
};
```

```tsx
// 함수

interface Add {
  (num1: number, num2: number): void;
}
// 괄호안에 있는것이 받는 인자이고 :다음에 있는것이 return 하는 값의 type이다

const add: Add = (x, y) => {
  console.log(x + y);
};

add(12, 423);
// 435
```

```tsx
// 클래스

interface Car {
  color: string;
  wheels: number;
  start(): void;
}

class Bmw implements Car {
  color;
  wheels = 4;
  constructor(c: string) {
    this.color = c;
  }
  start() {
    console.log("...go");
  }
}

const benz = new Bmw("green");
```

```tsx
// 확장

interface Car {
  color: string;
  wheels: number;
}

interface SuperCar extends Car { //extands를 사용해서 Car interface에다가 추가로 속성을 지정해주었다
  door: number;
  brand: string;
}

const kia: SuperCar = {
  color: "white",
  wheels: 4,
  door: 5,
  brand "Kia"
};
```
