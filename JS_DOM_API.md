# [JS] javascript 자바스크립트 DOM API

## DOM API (Document Object Model, Application Programming Interface)
(어플리케이션)웹사이트가 동작하도록 입력하는 프로그래밍 명령  
i.e. 자바스크립트에서 (DOM)HTML을 제어하는 여러가지 명령들(API)이다.  
```
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="./main.js"></script>
</head>
<body>
    <div class="box">BOX!</div>    
</body>
</html>
```
CSS 선택자(.box)를 통해 HTML부분에서 특정 요소를 찾아서 그것을 변수 boxEl에 할당한다.  
```
let boxEl = document.querySelector('.box');

console.log(boxEl);
```
하지만 브라우저가 위에서 아래로 HTML코드를 읽어 내려가는 특성으로  
HTML <script> 영역까지 코드를 읽고 콘솔창에 값을 출력하는 오류가 발생된다.  
<img width="688" alt="스크린샷 2024-02-06 오전 7 42 19" src="https://github.com/hyunji1117/everyday_study/assets/151576407/8d17b7e1-fb6d-43a8-b85c-9a7780b6a297">
> 해당 값을 찾을 수 없다고 Null이 뜨게 된다.

여기서 script 코드에 defer를 추가하면 브라우저가 코드를 쭉 읽고 다시 <script>로 올라와서 요청한 값을 확인하여 출력하게 된다. 
(CSS .box > html class "box"를 가진 div요소를 찾아서 boxEl에 할당이 되어 출력)   
```
<title>Document</title>
<script defer src="./main.js"></script>		<!-- defer 추가 -->
```
<img width="688" alt="스크린샷 2024-02-06 오전 7 44 32" src="https://github.com/hyunji1117/everyday_study/assets/151576407/ea51768d-7076-4d0f-aa60-090936ad2684">

### DOM API  실행 과정
```
// HTML 요소(Element) 1개 검색/찾기
const boxEl = document.querySelector('.box');
/*
querySelector: 메소드
('.box'): class 선택자 인수
boxEl: box요소 약자

해당 CSS 선택자를 통해 찾아진 요소 중 가장 먼저 찾은 요소 하나만 반환하는 특징이 있다.
*/

// HTML (boxEl)요소에 메소드 추가 가능
boxEl.addEventListener();

// 명령어 addEventListener 메소드에 인수(Arguments, 데이터X) 추가 가능
boxEl.addEventListener(1,2);

// 1 - 첫 번째 인수_이벤트(Event, 상황)
boxEl.addEventListener('click', 2);
/*
사용자가 boxEl를 클릭했을 때의 상황을 브라우저는 '이벤트'라고 본다.
i.e. 클릭이라는 상황이 일어나면 무언가를 하겠다는 의미로 사용되는 코드이다.
*/

// 2 - 두 번째 인수_핸들러(Handler, 실행할 함수)
boxEl.addEventListener('click', function (){
  console.log('click!');
});
/*
두 번째 인수에 익명 함수를 대신 넣어 데이터처럼 활용한다.
i.e. boxEl에 이벤트를 추가할지 듣고 있다가 클릭이 일어나면 익명 함수를 실행시킨다는 의미이다.  
*/
```

js에서 class 추가하기  
```
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script defer src="./main.js"></script>
</head>
<body>
    <div class="box">BOX!</div>    
</body>
</html>
```
let boxEl = document.querySelector('.box');

console.log(boxEl);

boxEl.addEventListener('click', function(){
  console.log('Click!');
  boxEl.classList.add('active');	// class추가!!
});
```
![GIFMaker_me](https://github.com/hyunji1117/everyday_study/assets/151576407/0bf32c97-d6d2-414d-a730-3ce54929b27f)
