## Type

Typescript에서는 Type을 지정할 수 있다

<hr>

- 선언

```ts
const [변수이름]: [변수의 타입] = [변수 할당 값];
// 이런식으로 타입을 지정한다
```

```ts
// Number Type
const n: number = 1452;
```

```ts
// String Type
const s: string = "type";
```

```ts
// Boolean Type
const b: boolean = true;
```

```ts
// Object Type
const o: object = { name: "gaon", age: 17 };
```

```ts
// Array Type
const a: number[] = [1, 42, 4, 5, 9];
const r: Array<string> = ["a", "B", "C", "d"];
```

```ts
// Tuple Type
const t: [number, string] = [123, "123"];
// 배열의 길이와 인덱스 값의 타입을 지정할 수 있다
```

```ts
// Enum Type
enum color {
  red,
  blue,
  yellow,
}
const c: color = color.red;
// 특정 값들의 집합이다
```

```ts
// Any Type
let a: any = "hi";
a = 1231;
```

```ts
// Union Type
const u: string | number = 123;
// 둘중 아무거나 사용할수 있는 타입이다
```
