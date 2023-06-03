## switch문 
### switch문은 if문이 switch문으로 대신 쓰일수 있을때 사용한다

``` js
// if문을 사용했을떄
const RealMadrid = {
    쿠르투아 : "No.1 GK",
    카르바할 : "No.2 DF",
    밀리탕 : "No.3 DF",
    알라바 : "No.4 DF",
    크로스 : "No.8 MF",
    벤제마 : "No.9 FW",
    모드리치 : "No.10 MF",
    발베르데 : "No.15 MF",
    비니시우스 : "No.20 FW",
    호드리구 : "No.21 FW",
    뤼디거 : "No.22 DF",
     };

const player = prompt("누구에 대해 알고 싶나요?");

if (player === "쿠르투아") {
    alert(RealMadrid.쿠르투아);
} else if (player === "카르바할") {
    alert(RealMadrid.카르바할);

} else if (player === "밀리탕") {
    alert(RealMadrid.밀리탕);

} else if (player === "알라바") {
    alert(RealMadrid.알라바);

} else if (player === "크로스") {
    alert(RealMadrid.크로스);

} else if (player === "벤제마") {
    alert(RealMadrid.벤제마);

} else if (player === "모드리치") {
    alert(RealMadrid.모드리치);
    
} else if (player === "발베르데") {
    alert(RealMadrid.발베르데);

} else if (player === "비니시우스") {
    alert(RealMadrid.비니시우스);

} else if (player === "호드리구") {
    alert(RealMadrid.호드리구);

} else if (player === "뤼디거") {
    alert(RealMadrid.뤼디거);
}
```

``` js
// switch문을 사용했을때
const RealMadrid = {
    쿠르투아 : "No.1 GK",
    카르바할 : "No.2 DF",
    밀리탕 : "No.3 DF",
    알라바 : "No.4 DF",
    크로스 : "No.8 MF",
    벤제마 : "No.9 FW",
    모드리치 : "No.10 MF",
    발베르데 : "No.15 MF",
    비니시우스 : "No.20 FW",
    호드리구 : "No.21 FW",
    뤼디거 : "No.22 DF",
     };
               // 값을 입력받는 함수
const player = prompt("누구에 대해 알고 싶나요?");

switch (player) {
  case "쿠르투아":
    alert(RealMadrid.쿠르투아);
    break;

  case "카르바할":
    alert(RealMadrid.카르바할);
    break;

  case "밀리탕":
    alert(RealMadrid.밀리탕);
    break;

  case "알라바":
    alert(RealMadrid.알라바);
    break;

  case "크로스":
    alert(RealMadrid.크로스);
    break;

  case "벤제마":
    alert(RealMadrid.벤제마);
    break;

  case "모드리치":
    alert(RealMadrid.모드리치);
    break;

  case "발베르데":
    alert(RealMadrid.발베르데);
    break;

  case "호드리구":
    alert(RealMadrid.호드리구);
    break;

  case "뤼디거":
    alert(RealMadrid.뤼디거);
    break; 
    }
// switch문을 사용했을때 좀더 코드가 간단해진다
```