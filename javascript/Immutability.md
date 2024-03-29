## 불변성(Immutability)

불변성의 개념은 값이나 상태를 변경할 수 없는 것이다

나는 불변성이라는 개념을 자바스크립트를 배울때 접하지 않고 리액트를 배울때 처음 접해봤다.
<br>
리액트에서는 배열이나 객체를 바꿀때 원래의 배열이나 객체를 바로 바꾸지 않고 새로운 배열이나 객체를 만들어서 바꾸어야 한다. 하지만 나는 왜 이런식으로 불변성을 지키면서 바꿔야하는지에 대해 궁금증이 생겨 이 글을 쓴다.

### 변수에 값 할당하기

변수에 값을 할당한다는 것은 값을 메모리에 저장하고 변수는 메모리의 주소를 가르키는 것이다

```js
let a = "hi, gaon";
```

위의 코드를 보면 "hi, gaon"이라는 값을 메모리에 저장하고 메모리의 주소를 변수 a가 가르키도록 한것이다

## primitive type

원시 타입의 종류로는 Boolean, String, Number, Null, undefined, Symbol이 있다
<br>
원시 타입은 값을 재할당 할때 값을 새로운 메모리 주소에 저장하고 변수에 새로운 메모리 주소를 가르키게 한다

```js
let name = "gaon";
name = "dahan";
```

위의 코드를 보면 "gaon"이라는 값을 메모리에 저장하고 메모리의 주소를 변수 name이 가르키도록 하고
<br>
새 메모리에 "dahan"이라는 값을 저장하고 새 메모리의 주소를 name이 가르키도록 한 코드이다

```js
let name = "gaon";
let newName = name;
name = "miri";

console.log(name); //miri
console.log(newName); //gaon
```

위의 코드를 보면 name에 "gaon"이라는 값을 할당하고 newName에 name을 할당한다 이것은 newName에 name이 가르키고 있는 메모리주소를 가르키는 것이다 그래서 나중에 "miri"라는 값을 새로운 메모리에 저장하고 주소를 name에 가르켜도 값이 변하지 않는다

## object type

오브젝트 타입의 종류로는 Array, Object, Function이 있다
<br>
오브젝트 타입은 값을 재할당 할때 원시 타입과는 다르게 새로운 메모리 주소에 값을 저장해 가르키지 않고 원래 변수가 가르키는 메모리 주소에서 값을 변경 한다

```js
let people = {
  name: "gaon",
};

let newPeople = people;

people.name = "sanghyuk";

console.log(newPeople.name); // sanghyuk
console.log(x === y); // true
```

위의 코드를 보면 메모리에 객체 값을 저장하고 people 변수에 메모리 주소를 가르키게 한다
<br>
newPeople에는 people 변수가 가르키는 메모리 주소를 가르키게 한다
<br>
people.name에 값을 바꿀때 원시 타입과 다르게 원래 메모리 주소에 저장된 값을 바꾼다

newPeople.name이 sanghyuk 인 이유는 newPeople은 people의 메모리 주소를 가르키는데 people의 name이 바뀔때 새로운 메모리 주소에 바꾼값을 할당하지 않고 원래 가르키고 있던 메모리 주소에서 바꾸었지 때문이다

그래서 x === y도 같은 메모리 주소를 가르키고 있기 때문에 true가 나온다

### 아니 그래서 불변성이 왜 중요한데?

불변성이 중요한 이유는 사용할 데이터가 어디서 어떻게 변하는지 알기 어렵기 때문이다
불변성을 지켜 코드를 짠다면 예상가능하고 신뢰할 수 있는 코드가 될 수 있다

### 리액트 불변성의 중요성

리액트에서 불변성이 중요한 이유는 리액트에서는 얕은 비교를 통해 업데이트를 결정 내리기 때문이다

얕은 비교는 기본 타입 데이터의 경우 값이 동일한지만 비교하고, 객체의 경우 참조(객체가 가르키는 메모리 주소가 같은지)만 비교한다.

예를 들자면 useState같은 경우도 상태를 업데이트 할때 이전값과 얕은비교를 통해 다르다면 state를 변경한다 하지만 불변성을 지키지 않고 그냥 값에서 변경한후 set함수를 실행 한다면 메모리 주소는 같으므로 리액트에서는 같다고 생각하여 state가 업데이트 되지 않고 렌더링도 되지 않는다
