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

여기서 script 코드에 defer를 추가하면 브라우저가 코드를 쭉 읽고 다시 script로 올라와서 출력하게 된다. 
(CSS .box > html class "box"를 가진 div요소를 찾아서 boxEl에 할당이 되어 출력)  
```
<title>Document</title>
<script defer src="./main.js"></script>		<!-- defer 추가 -->
```
<img width="688" alt="스크린샷 2024-02-06 오전 7 44 32" src="https://github.com/hyunji1117/everyday_study/assets/151576407/ea51768d-7076-4d0f-aa60-090936ad2684">
