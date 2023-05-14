# javascript
### javascript란?
#### Javascript는 HTML과 CSS로 만들어진 웹페이지를 동적으로 변경해주는 언어이다

### 변수 생성

|종류|설명|
|:--:|:--:|
|const|재할당 불가능|
|let|재할당 가능|
|var|중복 선언 가능|

``` js
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