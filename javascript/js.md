# javascript

### javascript란?

#### Javascript는 HTML과 CSS로 만들어진 웹페이지를 동적으로 변경해주는 언어이다

### 변수 생성

| 종류  |      설명      |
| :---: | :------------: |
| const | 재할당 불가능  |
|  let  |  재할당 가능   |
|  var  | 중복 선언 가능 |

```js
    const [변수이름] = [할당할 값];
    /* 예시 */
    const a = 30;
    /* a에 30을 할당*/
    const b = "apple";
    /* 변수에 문자나 문자열을 할당할때는 "를 사용한다*/

    let c = 30;

    c = 20;
    /*const와 다르게 let으로 변수을 생성하면 재할당이 가능하다*/
```

#### 변수를 생성할때 변수 이름에 공백이 들어가면 안된다 <br> 만약 변수이름이 길다면 camel case형식으로 작성하면 된다 ex. veryLongVariableName

<hr/>

### console.log

#### 무언가를 조합할때는 console.log를 사용한다

```js
const a = 10;
const b = 7;
const firstName = "gaon";
const lastName = " bang";
console.log(a + b);
/*17*/
console.log(firstName + lastName);
/*gaon bang*/
```

<hr/>

### boolean

#### js에서 boolean은 참과 거짓을 나타내기 위해 사용된다

| 종류  |         설명         |
| :---: | :------------------: |
| true  |  참을 나타낼때 사용  |
| false | 거짓을 나타낼때 사용 |

<hr/>

### null과 undefined

#### js에서 없음을 나타내는 값으로 두가지를 사용한다 하지만 각각 사용되는 목적이 다르다

```js
const null = null;
const undefined;

console.log(null);
console.log(undefined);

/*각각 null 과 undefined 나온다*/
```

null은 null이라는 값을 할당해야 null이나오고<br/>
undefined는 아무 값도 할당하지 않았을때 나온다

<hr/>

### object

#### property로 구성된 집합이다

```js
    /*이런식으로 사용한다*/
const [object 이름] = {
    [key 이름]: [값]
};
    /*예시*/
const human = {
    name: "이진헌",
    age: 17,
    height: "170cm"
};


    /*값을 수정할때*/
[object 이름].[key 이름] = [바꿀 값];

    /*예시*/
human.height = "168cm";

    /*새로운 키를 추가할때*/
[object 이름].[key 이름] = [값];

    /*예시*/
human.weight = "54kg";
```
