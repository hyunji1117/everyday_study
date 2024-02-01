# [JS] javascript 자바스크립트 함수  

## 함수(function)  
자바스크립트로 만들 수 있는 여러가지 특정 동작/기능들을 실제로 실행할 수 있는 코드의 집합이다.  
i.e. 명령들을 감싸고 있는 집합을 뜻한다. 그리고 프로그래밍은 거의 함수로 이루어져 있다.  
```
function helloEve(){ // 함수 선언할 때는 function 키워드 명시. 그리고 원하는 함수 이름'helloEve' 작성. (소괄호 1set){중괄호 1set} 기호 사용. => 코드들의 집합
  // 실행 코드 (코드 내용)
  console.log(123); // {중괄호 1set} 사이에 명령 코드를 넣는다. i.e. 여기에서는 console창에 log를 남기고, 그 데이터는 숫자 123 임을 명시하는 것이다. => 코드 내용
};

// 함수 호출해서 실행
helloEve(); // 123
```

### 반환(return)  
함수 내에서 return 함수를 사용하여 자바스크립트 데이터를 함수 밖으로 내보내는 것.  
그리고 내보내진 함수를 새로운 변수에 할당해서 추가적으로 사용할 수 있다.  
```
function returnAge() {
  return 38;
};

let a = returnAge(); // 반환된 데이터'123'을 키워드let을 사용하는 함수a가 받아서 returnEve함수가
		    //호출되면 (호출을 하면 실행이 되어야 한다.)
console.log(a); // 함수에서 반환된 123 출력
```
<img width="685" alt="스크린샷 2024-02-02 오전 8 19 22" src="https://github.com/hyunji1117/everyday_study/assets/151576407/20647d00-e5cb-4939-b9d2-9d1dd4d92caa">

함수가 호출되는 부분 sum(7, 4)에서 데이터를 집어넣고  
데이터를 받아줄 변수 sum(a, b)  
```
// 함수 선언
function sum(a,b) { // (2-1) 이 함수 내에서 사용하는 변수를 각각 a, b 이름으로 정의하였는데, 이 변수를 매개변수(Parameters)하고 한다. 
  return a+b; // (2-2) 내부 처리 및 함수 실행을 통해 밖으로 내보내 진다. 
};

// 재사용
let a = sum(7,4); // (1) 데이터 인수들을 함수가 받아 (3) 그 값을 변수a에 담아 밖으로 내보낸다. **7과 4는 매개변수를 받는 인수(Arguments)라고 한다. 
let b = sum(6,3);
let c = sum(2,4);

console.log(a,b,c); // (4) 변수 a,b,c 출력 > 11,9,6
```
<img width="686" alt="스크린샷 2024-02-02 오전 8 54 30" src="https://github.com/hyunji1117/everyday_study/assets/151576407/965a0b1d-0946-4b35-9620-b63393ed0ce8">