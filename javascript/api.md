## api

### js에서 api를 사용하는 방법

#### 현재 위치와 날씨를 가져오는 api이다

```js
function onGeoOk(position) {
  const lat = position.coords.latitude;
  const lon = position.coords.longitude;
  // api url이다
  const url = `https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lon}&appid=${API_KEY}&units=metric`;
  fetch(url) //fetch를 사용하면 url 주소로 요청을 보낸다
    //fetch를 쓰면 비동기로 처리 된다
    .then((response) => response.json()) //응답이 오면 response에 할당이 되고 .json()을 사용해서 js에서 사용할수 있게 만든다
    .then((data) => {
      const weather = document.querySelector("#weather span:first-child");
      const city = document.querySelector("#weather span:last-child");
      city.innerText = data.name; // 위치를 저장
      weather.innerText = `${data.weather[0].main} / ${data.main.temp}`; //날씨와 온도 저장
      console.log("then");
    });
}
```
