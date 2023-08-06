## sass

Syntactically Awesome Style Sheets(문법적으로 놀라운 스타일 시트)의 약자로, CSS pre-processor 중 하나로서 기존의 CSS를 효율적이고 간편하게 만들수 있게 해준다

<hr>

#### .sass & . scss

- sass에서는 2개의 확장자를 지원한다
- .sass와 .scss는 문법이 완전 다르다
- 대부분 .scss 문법을 많이 사용한다

<hr>

- #### 변수

```scss
$blue: #228be6;
$gray: #495057;
$pink: #f06595;

.test {
  background: $gray;
}
```

이런식으로 변수를 선언 할때는 `$변수이름: 값 할당` 형식으로 선언하고 사용할수 있다

<hr>

- #### mixin

mixin은 재사용 가능한 스타일 패턴을 정의하는 기능으로, 함수처럼 사용할 수 있다

```scss
$blue: #228be6;

@mixin button-color($color) {
  background: $color;
  &:hover {
    background: lighten($color, 10%);
  }
  &:active {
    background: darken($color, 10%);
  }
}

@include button-color($blue);
```

mixin을 선언할때는 @mixin을 입력하고 함수처럼 선언하면 된다
<br>
mixin을 사용할때는 @include를 입력하고 함수를 사용하는것 처엄 사용하면 된다
