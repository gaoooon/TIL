## generic

기존의 함수의 타입을 정의할때는 타입을 명시적으로 정의해 예상 밖의 타입 오류를 방지한다
<br>
하지만 여러 타입을 유연하게 함수에 사용 할 수 있게 할떄 사용하는것이 generic이다
<br>
쉽게 생각하면 변할수 있는 타입이라고 생각하면 된다

제네릭을 사용하면 타입을 유연하게 사용할수 있다

코드를 통해 알아보자

```ts
function log<T>(a: T): void {
  console.log(a);
}

log<string>("hi 나 가온");
```

꺾새와 영어를 사용해 제네릭을 이용 할 수 있다
<br>
제네릭은 특이하게 사용할때 타입을 지정해 준다

interface에도 사용할수 있다

```ts
interface user<T extends string | number> {
  name: string;
  age: number;
  birth: T;
}

const gaon: user<number> = { name: "gaon", age: 18, birth: 810 };
const jinheon: user<string> = { name: "jinheon", age: 18, birth: "2월 22일" };
```

### extends

extends를 사용하여 유연하지만 제한적이게 사용할수 있다

```ts
function log<T extends string | number>(a: T): void {
  console.log(a);
}

log<string>("hi 나 가온");
log<number>(555);
log<boolean>(false); // error!
```
