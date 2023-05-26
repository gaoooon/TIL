## preventDefault

### 기본동작을 방지하는 역할을 한다

#### 예들들면 \<a> 태그의 기본동작은 클릭시 페이지를 이동하는것이고 \<form> 태그의 기본동작은 submit하면 새로고침한다는 것이 있다

##### 사용법

```js
// submit의 기본동작을 방지하고 있다
function handleSubmitedForm(event) {
  event.preventDefault();
}

loginForm.addEventListener("submit", handleSubmitedForm);
```
