## 미디어 쿼리

### 미디어 쿼리는 반응형웹을 만들때 사용한다

## 반응형웹이란?

### 반응형웹이란 하나의 웹사이트에서 PC, 스마트폰, 태블릿 PC 등 접속하는 디스플레이의 종류에 따라 화면의 크기가 자동으로 변하도록 만든것이다

```css
// 기본구조
@media (조건) {
    실행 코드
}
```

```css
/* 예시 */
.div {
  width: 800px;
  height: 400px;
  background-color: red;
}
@media (max-width: 500px) {
  .div {
    background-color: blue;
    height: 200px;
  }
}
```
