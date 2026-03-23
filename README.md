# 모던 자바스크립트로 배우는 리액트 입문(한빛미디어, 2022)

## Day 1 (Modern Javascript)

### 객체 속성값 변경 및 추가

```jsx
// 객체 정의
const obj1 = {
	name: "누시다",
	age: 24
};
console.log(obj1); // {name: "누시다", age: 24}

// 속성값 변경
obj.name = "Nushida";
console.log(obj1); // {name: "Nushida", age: 24}

// 속성 추가
obj1.address = "Tokyo";
console.log(obj1); // {name: "Nushida", age: 24, address: "Tokyo"}
```

### 배열값 변경, 추가

```jsx
// 배열 정의
const arr1 = ["dog", "cat"];
console.log(arr1); // ["dog", "cat"]

// 첫 번째 값 변경
arr1[0] = "bird";
console.log(arr1); // ["bird", "cat"]

// 값 추가
arr1.push("monkey");
console.log(arr1); // ["bird", "cat", "monkey"]
```

→ 리액트에서는 const를 가장 많이 사용, state로 관리하지 않으면서 처리 도중 값을 덮어 써야 하는 변수만 let으로 선언

### 기존 문자열과 변수 결합 방법

```jsx
// 이름을 저장한 변수
const name = "누시다";

// 나이를 저장한 변수
const age = 24;

// '내 이름은 누시다입니다. 나이는 24세입니다.' 라고 표기하는 경우
const message = "내 이름은 " + name + "입니다. 나이는 " + age + "세입니다.";

console.log(message); // 내 이름은 누시다입니다. 나이는 24세입니다.
```

### 템플릿 문자열 이용

```jsx
// 이름을 저장한 벼수
const name = "누시다";

// 나이를 저장한 변수
const age = 24;

// '내 이름은 누시다입니다. 나이는 24세입니다.'라고 표시하는 경우
const message = `내 이름은 ${name}입니다. 나이는 ${age}세입니다.`;

console.log(message);
```

### 함수 호출과 계산 실행

```jsx
// '안녕하세요!'를 반환하는 함수
function sayHello(){
	return "안녕하세요!";
}

// 월을 나타내는 숫자를 저장한 변수
const month = 1;

// 템플릿 문자열 안에서의 함수 호출 및 곱셈 실행
const message = `여러분 ${sayHello()}! 오늘부터 ${month * 3}월입니다!`;

console.log(message); // 여러분 안녕하세요! 오늘부터 3월입니다!
```

### 화살표 함수 () ⇒ {}

```jsx
// 화살표 함수 정의
const func2 = (value) => {
	return value;
};

// 실행 결과 출력
console.log(func2("func2입니다")); // func2입니다
```

### ()를 이용해 한 행으로 모으기

```jsx
// 괄호로 감싸서 모은 뒤 생략해서 반환
const func5 = (val1, val2) => (
	{
		name: val1,
		age: val2
	}
)

// 실행 결과 출력
console.log(func5("누시다", 24)); // {name: "누시다", age: 24)
```

### 분할대입 {} []

```jsx
const myProfile = {
	name: "누시다",
	age: 24
};

// 객체 분할 대입
const {name, age} = myProfile;

const message = `내 이름은 ${name}입니다. 나이는 ${age}세입니다.`;
console.log(message); // 내 이름은 누시다입니다. 나이는 24세입니다.

// 콜론으로 다른 변수명을 이용
const {name: newName, age: newAge} = myProfile;

const message = `내 이름은 ${newName}입니다. 나이는 ${newAge}세입니다.`;

console.log(message); // 내 이름은 누시다입니다. 나이는 24세입니다.

// 배열 인덱스를 지정해서 대입
const myProfile = ["누시다", 24];

const message = `내 이름은 ${myProfile[0]}입니다. 나이는 ${myProfile[1]}세입니다.`;

console.log(message); // 내 이름은 누시다입니다. 나이는 24세입니다.

// 배열에 분할 대입
const myProfile = ["누시다", 24];

const [name, age] = myProfile;

const message = `내 이름은 ${name}입니다. 나이는 ${age}세입니다.`;

// 배열에서 필요한 요소만 추출
const [name] = myProfile;
```

### 디폴트값 “=”

```jsx
// 메세지를 출력하는 함수
const sayHello = (name) => console.log(`${name}님 안녕하세요!`);

sayHello(); // undefined님 안녕하세요!

// 디폴트값 설정
const sayHello = (name = "누시다") => console.log(`${name}님 안녕하세요!`);

sayHello(); // 누시다님 안녕하세요!
sayHello("게스트"); // 게스트님 안녕하세요!
```

### 객체 분할 대입의 디폴드값

```jsx
// name을 삭제
const myProfile = {
	age: 24	
};

// 존재하지 않는 name
const {name} = myProfile;

const message = `${name}님 안녕하세요!`;
console.log(message); // undefined님 안녕하세요!

// 분할 대입 시의 디폴트값을 설정
const myProfile = {
	age: 24
};

const {name = "게스트"} = myProfile;

const message = `${name}님, 안녕하세요!`;
console.log(message); // 게스트님, 안녕하세요!
```

### 스프레드 구문 …

→ 스프레드 구문은 …과 같이 점 세 개를 연결해서 사용. 배열에 이용함으로써 내부 요소를 순차적으로 전개할 수 있음.

```jsx
const arr1 = [1, 2];
console.log(arr1); // [1, 2]
console.log(...arr1); // 1 2
```

### 일반적인 함수와 스프레드 구문 비교

```jsx
const arr1 = [1, 2];

const summaryFunc = (num1, num2) => console.log(num1 + num2);

// 일반적으로 배열값을 전달하는 경우
summaryFunc(arr1[0], arr1[1]); / 3

// 스프레드 구문을 이용하는 방법
summaryFunc(...arr1); // 3
```

### 요소 모으기

```jsx
const arr2 = [1, 2, 3, 4, 5];

// 분할 대입 시 남은 요소를 '모은다' 어렵다
const [num1, num2, ...arr3] = arr2;

console.log(num1);
console.log(num2);
console.log(arr3);
```

### 스프레드 구문을 이용해 새로운 배열 생성

```jsx
const arr4 = [10, 20];
const arr5 = [30, 40];

// 스프레드 구문을 이용해 복사
const arr6 = [...arr4];

console.log(arr4); // [10, 20]
console.log(arr6); // [10, 20]
```

### 두 개의 배열 결합

```jsx
const arr4 = [10, 20];
const arr5 = [30, 40];

const arr7 = [...arr4, ...arr5];

console.log(arr7); // [10, 20, 30, 40]
```

### 등호를 이용해서 복사하지 마라

→ 배열이나 객체 등 ‘오브젝트 타입’이라 불리는 변수는 등호를 이용해서 복사하면 **참조값 역시 상속**되기 때문에 예상치 못한 동작을 일으킬 수 있음.

### 스프레드 구문을 이용한 복사

```jsx
const arr4 = [10, 20];

// 스프레드 구문을 이용해 복사
const arr8 = [...arr4];

// arr8의 처음 요소를 100으로 덮어 씀
arr8[0] = 100;

console.log(arr4); // [10, 20]
console.log(arr8); // [100, 20]
```

### 객체 생략 표기법

→ **객체의 속성명**과 **설정할 변수명**이 같으면 생략할 수 있음

```jsx
const name = "누시다";
const age = 24;

// 생략 표기법
const user = {
	name,
	age
};

console.log(user); // {name: '누시다', age: 24}
```

### map, filter

```jsx
// 기존 for문은 복잡하고 코드 양도 늘어남
// 배열 정의
const nameArr = ["누시다", "사키오카", "고토"];

// for 문을 이용한 배열 처리
for (let index = 0; index < nameArr.length; index++){
	console.log(nameArr[index]);
};
// 누시다
// 사키오카
// 고토
```

### map 함수

```jsx
const nameArr = ["누시다", "사키오카", "고토"];

// 1
const nameArr2 = nameArr.map();

// 2
const nameArr2 = nameArr.map(() => {});

// 3
const nameArr2 = nameArr.map((name) => {
	return name;
});

console.log(nameArr2);
```

### map 함수 이용

```jsx
// 배열 정의
const nameArr = ["누시다", "사키오카", "고토"];

// map을 이용한 배열 처리
nameArr.map((name) => console.log(name));
// 누시다
// 사키오카
// 고토
```

### filter 함수 이용 방법

→ map함수와 비슷하지만 return 뒤에 조건식을 입력해서 일치하는 것만 반환함

```jsx
// 배열 정의
const numArr = [1, 2, 3, 4, 5];

// 홀수(2로 나누어 나머지가 1)만 추출
const newNumArr = numArr.filter((num) => {
	return num % 2 === 1;
});

console.log(newNumArr); // [1, 3, 5]
```

### for문의 index를 이용해 요소를 순서대로 추출

```jsx
const nameArr = ["누시다", "사키오카", "고토"];

// 정의한 index를 이용
for (let index = 0; index < nameArr.length; index++){
	console.log(`${index + 1}번째는 ${nameArr[index]}입니다`);
};
// 1번째는 누시다입니다
// 2번째는 사키오카입니다
// 3번째는 고토입니다
```

### map 함수의 인수를 이용해 요소 순서대로 추출

```jsx
const nameArr = ["누시다", "사키오카", "고토"];

// 두 번째 인수에 index를 넣는다.
nameArr.map((name, index) => console.log(`${index + 1}번째는 ${name}입니다`));
// 1번째는 누시다입니다
// 2번째는 사키오카입니다
// 3번째는 고토입니다
```

### map 예시

```jsx
// 누시다, 사키오카, 고토의 이름이 저장된 배열이 있다.
// 누시다 이외의 이름 뒤에는 존칭인 '님'을 붙인 새로운 배열을 생성하자.

const nameArr = ["누시다", "사키오카", "고토"];

const newNameArr = nameArr.map((name) => {
	if (name === "누시다") {
		return name;
	} else {
		return `${name}님`;
	}
});

console.log(newNameArr); // ['누시다', '사키오카님', '고토님']
```

### 삼항 연산자

→ 조건 ? 조건이 true일 때의 처리 : 조건이 false일 때의 처리

```jsx
// 1은 0보다 크므로 true, 따라서 :의 왼쪽이 설정된다
const val1 = 1 > 0 ? "true입니다" : "false입니다";

console.log(val1);
```

### 입력값에 대한 메시지 출력

```jsx
const printFormattedNum = (num) => {
	const formattedNum = typeof num === "number" ? num.toLocaleString() : "숫자를 입력 하십시오";
	console.log(formattedNum);
};

printFormattedNum(1300); // 1,300
printFormattedNum("1300"); // 숫자를 입력 하십시오

// typeof ~는 변수 등의 타입을 판정
// toLocaleString()은 숫자를 세 자리씩 콤마로 구분해서 변환함
```

### 함수 return부분에 삼항 연산자 이용

```jsx
const checkSumOver100 = (num1, num2) => {
	return num1 + num2 > 100 ? "100을 넘었습니다!" : "허용 범위 안입니다!";
}

console.log(checkSumOver100(50,40)); // 허용 범위 안입니다!
console.log(checkSumOver100(50,70)); // 100을 넘었습니다!
```

### 논리연산자

```jsx
// 논리 연산자를 이용한 조건 분기
const flag1 = true;
const flag2 = false;

if (flag1 || flag2) {
	console.log("두 플래그 중 어느 하나는 true입니다");
}

if (flag1 && flag2) {
	console.log("두 플래그가 모두 true입니다");
}

// 두 플래그 중 어느 하나는 true입니다
```

### ||이용(null 설정)

```jsx
// 케이스 1
const num = null;
const fee = num || "금액을 설정하지 않았습니다";

console.log(fee); // 금액을 설정하지 않았습니다

// 케이스 2
const num = 100;
const fee = num || "금액을 설정하지 않았습니다";

console.log(fee); // 100
```

→ 논리 연산자 ||이 연산자의 왼쪽이 **false**라고 판정하면 오른쪽을 반환함(null, undefined, 0 등은 자바스크립트에서 false로 판정)

→ 반대로 왼쪽이 true면 왼쪽을 반환함

### 논리 연산자를 이용한 조건 분기

```jsx
const flag1 = true;
const flag2 = false;

if (flag1 || flag2) {
	console.log("두 플래그 중 어느 하나는 true입니다");
}
// 왼쪽이 false이면 오른쪽을 반환, 왼쪽이 true이면 왼쪽을 반환
```

### &&이용(100 설정)

```jsx
const num2 = 100;
const fee2 = num2 && "무언가가 설정되었습니다";

console.log(fee2); // 무언가가 설정되었습니다
```

→ 논리 연산자 &&은 **왼쪽을 true로 판정하면 오른쪽을 반환**(||과 반대)

### falsy, truthy, nullish

→ 암묵적으로 true로 변환되는 값을 truthy, false로 변환되는 값을 falsy라고 부름

→ 0이나 “”(빈 문자)는 falsy, [ ](빈 배열)이나 { }(빈 객체)는 truthy임

→ null과 undefined로 판정되는 것은 nullish라고 부름

## Day 2 (자바스크립트에서 DOM 조작)
### 모형 | index.html

```jsx
<!DOCTYPE html>
<html>
    <head>
        <title>JavaScript에서의 DOM 조작</title>
        <meta charset="UTF-8" />
        <link rel="stylesheet" href="src/styles.css" />
    </head>

    <body>
        <h1 id="title">Hello World!!</h1>
        <div class="container">
            <p>영역 1입니다</p>
        </div>
        <div class="container">
            <p>영역 2입니다</p>
        </div>
        <script src="src/index.js"></script>
    </body>
</html>
```

### 템플릿 | styles.css

```jsx
.container {
    border: solid 1px #ccc;
    padding: 16px;
    margin: 8px;
}
```

### 요소 얻기 | index.js

```jsx
 // getElementById 사용
const title1 = document.getElementById("title");
console.log(title1);
// <h1 id="title">Hello World!!</h1>
```

→ 

```jsx
//querySelector 사용
const title2 = document.querySelector("#title");
console.log(title2);
// <h1 id="title">Hello World!!</h1>
```

→

### 클래스명으로 엘리먼트 얻기

```jsx
// getElementsByClassName 사용
const containers = document.getElementsByClassName("container");
console.log(containers);
```

→

### querySelector를 이용한 엘리먼트 얻기

```jsx
// querySelector 사용
const container = document.querySelector(".container");
console.log(container);
```

→ 클래스명일 때는 .을 붙임

### querySelectorAll을 이용한 엘리먼트 얻기

```jsx
// querySelectorAll 사용
const containers = document.querySelectorAll(".container");
console.log(containers);
```

→ querySelectorAll을 사용하면 일치하는 엘리먼트를 모두 얻음

### DOM 작성

```jsx
// div 생성
const divEl = document.createElement("div");
// p 생성
const pEl = document.createElement("p");
// h2 생성
const h2El = document.createElement("h2");

// div 태그 아래 태그 추가(뒤에)
divEl.appendChild(pEl);
divEl.appendChild(h2El);

console.log(divEl);
```

```jsx
// div 생성
const divEl = document.createElement("div");
// p 생성
const pEl = document.createElement("p");
// h2 생성
const h2El = document.createElement("h2");

// div 태그 태그 추가(맨 앞)
divEl.prepend(pEl);
divEl.prepend(h2El);

console.log(divEl);
```

### 버튼 설정

```jsx
// button 태그 생성
const buttonEl = document.createElement("button");

// 버튼 라벨 설정
buttonEl.textContent = "버튼";

// 영역 1의 div 태그 얻기
const div1El = document.querySelector(".container");

//div 태그 아래에 button 태그를 추가
div1El.appendChild(buttonEl);
```

### h1 태그 삭제

```jsx
const h1El = document.getElementById("title");

// body 태그 얻기
const bodyEl = document.querySelector("body");

// body 태그 아래부터 삭제
bodyEl.removeChild(h1El);
```

### body 아래 모두 삭제

```jsx
// body 태그 얻기
const bodyEl = document.querySelector("body");

// body 태그 아래부터 삭제
// 자녀 요소를 모두 삭제할 때는 textContent에 null을 지정
bodyEl.textContent = null;
```

### 간단 메모 애플리케이션

### index.html

```html
<!DOCTYPE html>
<html>
    <head>
        <title>간단 메모 애플리케이션</title>
        <meta charset="UTF-8" />
        <link rel="stylesheet" href="src/styles.css" />
    </head>

    <body>
        <h1 id="title">간단 메모 애플리케이션</h1>
        <input id="add-text" />
        <button id="add-button">추가</button>
        <div class="container">
            <p>메모 목록</p>
            <ul id="memo-list"></ul>
        </div>
        
        <script src="src/index.js"></script>
    </body>
</html>
```

### styles.css

```css
.container {
    border: solid 1px #ccc;
    padding: 16px;
    margin: 8px;
}

li > div {
    display: flex;
    align-items: center;
}

button {
    margin-left: 16px;
}
```

### index.js

```jsx
// 추가 버튼 클릭 시 실행하는 함수
const onClickAdd = () => {
    // 텍스트 박스의 엘리먼트를 얻는다.
    const textEl = document.getElementById("add-text");

    // 텍스트 박스의 값을 얻는다.
    const text = textEl.value;

    // 텍스트 박스를 초기화한다(공백)
    text.value = "";

    // li 태그 생성
    const li = document.createElement("li");

    // div 태그 생성
    const div = document.createElement("div");

    // p 태그 생성(텍스트 박스의 문자 설정)
    const p = document.createElement("p");
    p.textContent = text;

    // button 태그 생성(라벨: [삭제])
    const button = document.createElement("button");
    button.textContent = "삭제";
    
    // 버튼 클릭 시 행을 삭제하는 처리
    button.addEventListener("click", () => {
        // 삭제 대상 행(li)을 얻는다.
        // closest는 부모 요소와 일치하는 문자열을 찾는 메서드
        const deleteTarget = button.closest("li");

        // ul 태그 아래에서 앞서 특정한 행을 삭제
        document.getElementById("memo-list").removeChild(deleteTarget);
    });

    // div 태그 아래에 p 태그와 button 태그 설정
    div.appendChild(p);
    div.appendChild(button);

    // li 태그 아래에 div 태그 설정
    li.appendChild(div);

    // 메모 목록 리스트에 li 태그 설정
    document.getElementById("memo-list").appendChild(li);
};

// [추가] 버튼 클릭 시 onClickAdd 함수를 실행하도록 등록
document
    .getElementById("add-button")
    .addEventListener("click", () => onClickAdd());
```
## Day 3 (리액트 기본)

```jsx
// 새 프로젝트를 만드는 경우
npx create-react-app [프로젝트명]

// 로컬 환경에서 명령어 실행
cd [프로젝트폴더명]
npm start
```

- 리액트는 JSX 표기법을 사용함

### ReactDom import | index.js

```jsx
import ReactDOM from "react-dom";
```

### 함수 정의 | index.js

```jsx
import ReactDOM from "react-dom";

// App이라는 이름으로 화살표 함수를 이용해 함수를 준비
// 우선 null을 반환하는 함수로 정의
const App = () => {
	return null;
}
```

### [JSX규칙] 리액트 17에서 리액트 18로 바뀜👺👺👺

```jsx
import React from "react";
import { createRoot } from "react-dom/client";

const App = () => {
    return (
        <div>
            <h1>안녕하세요!</h1>
            <p>잘 지내시죠?</p>
        </div>
    );
};

const root = createRoot(document.getElementById("root"));
root.render(<App />);
```

→ 여러 줄을 표시하고 싶을 때는 (<></>);사이에 집어넣음

→ import { createRoot} from “react-dom/client”; 이건 잘 모르겠음

### Fragment 사용

```jsx
import React from "react";
import { createRoot } from "react-dom/client";
import { Fragment } from "react";

const App = () => {
    return (
        <fragment>
            <h1>안녕하세요!</h1>
            <p>잘 지내시죠?</p>
        </fragment>
    );
};

const root = createRoot(document.getElementById("root"));
root.render(<App />);
```

→ 리액트에서 제공하는 fragment를 사용해도 된다고 함

→ fragment를 생략하고 빈칸으로 해도 괜찮음

### 컴포넌트 사용 | App.jsx 추가 생성

```jsx
// 다른 파일에서도 사용 가능하도록 export 해야 함
export const App = () => {
    return (
        <>
            <h1>안녕하세요!</h1>
            <p>잘 지내시죠?</p>
        </>
    );
}
```

→ 컴포넌트 파일의 확장자는 .jsx를 사용할 것을 권장

### 이벤트와 스타일

→ 버튼을 클릭했을 때의 이벤트는 보통 onclick으로 작성

→ 리액트에서는 이벤트 등을 **캐멀케이스(단어가 연결되는 부분을 대문자로 표기)**로 작성함

```jsx
// alert 기능 구현
export const App = () => {
    // 버튼 클릭 시 실행되는 함수 정의
    const onClickButton = () => {
        alert();
    };

    return (
        <>
            <h1>안녕하세요!</h1>
            <p>잘 지내시죠?</p>
            <button onClick={onClickButton}>버튼</button>
        </>
    );
};
```

### 글자를 빨간색으로 변경

```jsx
export const App = () => {
    // 버튼 클릭 시 실행되는 함수 정의
    const onClickButton = () => {
        alert();
    };

    return (
        <>
		        // style 추가
            <h1 style={{color: "red" }}>안녕하세요!</h1>
            <p>잘 지내시죠?</p>
            <button onClick={onClickButton}>버튼</button>
        </>
    );
};
```

### p 태그의 글자 색과 크기 변경

```jsx
export const App = () => {
    // 버튼 클릭 시 실행되는 함수 정의
    const onClickButton = () => {
        alert();
    };
    
		// CSS 객체
    const contentStyle = {
        color: "blue",
        fontSize: "20px"
    };

    return (
        <>
            <h1 style={{color: "red" }}>안녕하세요!</h1>
            <p style={contentStyle}>잘 지내시죠?</p>
            <button onClick={onClickButton}>버튼</button>
        </>
    );
};
```

### Props

```jsx
export const App = () => {
    // 버튼 클릭 시 실행되는 함수 정의
    const onClickButton = () => {
        alert();
    };
	
		// CSS 객체
    const contentStyle = {
        color: "blue",
        fontSize: "20px"
    };
    // 분홍색용으로 추가
    const contentPinkStyle = {
        color: "Pink",
        fontSize: "20px"
    };

    return (
        <>
            <h1 style={{color: "red" }}>안녕하세요!</h1>
            <p style={contentStyle}>잘 지내시죠?</p>
            <p style={contentPinkStyle}>잘 지냅니다!</p>
            <button onClick={onClickButton}>버튼</button>
        </>
    );
};
```

### p 태그 부분 복사 | ColoredMessage.jsx

```jsx
export const ColoredMessage = () => {
    const contentStyle = {
        color: "blue",
        fontSize: "20px"
    };

    return <p style={contentStyle}>잘 지내시죠?</p>;
};
```

### ColoredMessage 임포트 | App.jsx

```jsx
// 추가
import { ColoredMessage } from "./components/ColoredMessage";

export const App = () => {
    // 버튼 클릭 시 실행되는 함수 정의
    const onClickButton = () => {
        alert();
    };

    const contentPinkStyle = {
        color: "Pink",
        fontSize: "20px"
    };

    return (
        <>
            <h1 style={{color: "red" }}>안녕하세요!</h1>
            // 추가
            <ColoredMessage color="blue" message="잘 지내시죠?" />
            <p style={contentPinkStyle}>잘 지냅니다!</p>
            <button onClick={onClickButton}>버튼</button>
        </>
    );
};
```

→ Props를 사용하려면 Props를 전달하는 쪽의 컴포넌트(App.jsx)와 전달받는 쪽의 컴포넌트(ColoredMessage.jsx) 모두를 수정해야 함

→ 색상(color)과 메시지(message)를 전달

### Prop를 객체로 받음 | ColoredMessage.jsx

```jsx
export const ColoredMessage = (props) => {
    console.log(props);
    // {color: "blue", message: "잘 지내시죠?"}
    const contentStyle = {
        color: "blue",
        fontSize: "20px"
    };

    return <p style={contentStyle}>잘 지내시죠?</p>;
};
```

### App.jsx

```jsx
import { ColoredMessage } from "./components/ColoredMessage";

export const App = () => {
    // 버튼 클릭 시 실행되는 함수 정의
    const onClickButton = () => {
        alert();
    };

    return (
        <>
            <h1 style={{color: "red" }}>안녕하세요!</h1>
            <ColoredMessage color="blue" message="잘 지내시죠?" />
            <ColoredMessage color="pink" message="잘 지냅니다!" />
            <button onClick={onClickButton}>버튼</button>
        </>
    );
};
```

### 텍스트를 children으로 전달 | App.jsx

```jsx
import { ColoredMessage } from "./components/ColoredMessage";

export const App = () => {
    // 버튼 클릭 시 실행되는 함수 정의
    const onClickButton = () => {
        alert();
    };

    return (
        <>
            <h1 style={{color: "red" }}>안녕하세요!</h1>
            <ColoredMessage color="blue">잘 지내시죠?</ColoredMessage>
            <ColoredMessage color="pink">잘 지냅니다!</ColoredMessage>
            <button onClick={onClickButton}>버튼</button>
        </>
    );
};
```

### children으로 메시지 받기 | ColoredMessage.jsx

```jsx
export const ColoredMessage = (props) => {
    console.log(props);
    // {color: "blue", message: "잘 지내시죠?"}
    const contentStyle = {
        color: props.color,
        fontSize: "20px"
    };

    return <p style={contentStyle}>{props.children}</p>;
};
```

### Props 분할 대입(Props를 destructure한다)

```jsx
export const ColoredMessage = (props) => {
		// Props 분할 대입
    const { color, children } = props;
    
    const contentStyle = {
        color: color, // props. 불필요
        fontSize: "20px"
    };
		// props. 불필요
    return <p style={contentStyle}>{children}</p>;
};
```

### 생략 표기법, 인수 단계에서 전개

```jsx
// 인수의 ( ) 단계에서 분할 대입
export const ColoredMessage = ({ color, children }) => {
    
    const contentStyle = {
        color, // 생략 표기법 사용 가능
        fontSize: "20px"
    };

    return <p style={contentStyle}>{children}</p>;
};
```

### State(useState)

→ 화면의 표시하는 데이터나 길이가 변하는 상태 등을 모두 State로 관리함

### 기본서식

```jsx
import { useState } from "react";
```

### useState 사용 예

```jsx
const [num, setNum] = useState();
```

### state 초깃값 설정 방법

```jsx
const [num, setNum] = useState(0);
```

### 카운트 업 기능 구현

```jsx
// 수치 state를 정의해서 화면에 표시하고 버튼 클릭 시 카운트업하는 기능
import { useState } from "react"; // 기본서식
import { ColoredMessage } from "./components/ColoredMessage";

export const App = () => {
    // state 정의
        const [num, setNum] = useState(0); // 추가

    // 버튼 클릭 시 실행되는 함수 정의
    const onClickButton = () => {
        alert();
        setNum(num+1); // 추가
    };

    return (
        <>
            <h1 style={{color: "red" }}>안녕하세요!</h1>
            <ColoredMessage color="blue">잘 지내시죠?</ColoredMessage>
            <ColoredMessage color="pink">잘 지냅니다!</ColoredMessage>
            <button onClick={onClickButton}>버튼</button>
            <p>{num}</p>
        </>
    );
};
```

### 재렌더링과 부작용

→ State 업데이트 시 컴포넌트가 재렌더링되어 함수 컴포넌트가 다시 처음부터 실행된다

### useEffect 초깃값 설정 방법

```jsx
import { useEffect } from "react";
```

### useEffect 선언

```jsx
useEffect(실행하는 함수[, 의존하는 값]);
```

→ useEffect의 역할은 어떤 값이 변했을 때에 한해서만 어떤 처리를 실행하는 기능

### export 종류

### export 측(normal export)

```jsx
export const SomeComponent = () => {};
```

### import 측(normal export)

```jsx
import { SomeComponent } from "./SomeComponent";
```

### default export

### export 측

```jsx
const SomeConponent = () => {};
export default SomeComponent;
```

### import 측

```jsx
import SomeComponent from "./SomeComponent";
```

### export 측

```jsx
const SomeComponent = () => {};
export default SomeComponent;
```

### import 측

```jsx
import Some from "./SomeComponent";

import { SomeComponent as Some } from "./SomeComponent";
```

## Day 4 (리액트와 CSS)

### CSS Modules

→ 리액트 개발의 경우 컴포넌트별로 CSS파일을 제공하는 경우가 많음

```jsx
export const CssModules = () => {
	return (
		<div>
			<p>CSS Modules입니다</p>
			<button>버튼</button>
		</div>
	);
};
```

### SCSS 파일 정의 | CssModules.module.css

```css
.container {
    border: solid 1px #aaa;
    border-radius: 20px;
    padding: 8px;
    margin: 8px;
    display: flex;
    justify-content: space-around;
    align-items: center;
}
.title {
    margin: 0;
    color: #aaa;
}
.button {
    background-color: #ddd;
    border: none;
    padding: 8px;
    border-radius: 8px;
    &:hover {
        background-color: #aaa;
        color: #fff;
        cursor: pointer;
    }
}
```


→ &:hover로 버튼에 마우스 커서를 올렸을 때 색과 포인터가 바뀌도록 설정

```jsx
import classes from "./CssModules.module.css";

export const CssModules = () => {
    return (
        <div className={classes.container}>
            <p className={classes.title}>CSS Modules입니다</p>
            <button className={classes.button}>버튼</button>
        </div>
    );
};
```

→ 임의의 이름(예제에서는 classes)으로 CSS를 import하고 각 태그의 className속성에 정의한 클래스를 지정함

→ CSS클래스명의 스코프는 컴포넌트 안으로 한정됨, 다른 컴포넌트에서 container라는 같은 이름으로 클래스명을 정의해도 충돌하지 않음

### Styled JSX

→ 적극적으로 채용하지는 않지만 Next.js에 표준으로 내장되어 있는 라이브러리임

```jsx
export const StyledJsx = () => {
    return (
        <>
            <div className="container">
                <p className="title">Styled JSX입니다</p>
                <button className="button">버튼</button>
            </div>

            <style jsx>{`
                .container {
                    border: solid 1px #aaa;
                    border-radius: 20px;
                    padding: 8px;
                    margin: 8px;
                    display: flex;
                    justify-content: space-around;
                    align-items:center;
                }
                .title {
                    margin: 0;
                    color: #aaa;
                }
                .button {
                    background-color: #ddd;
                    border: none;
                    padding: 8px;
                    border-radius: 8px;
                }
            `}</style>
        </>
    )
}
```


### style 태그 사용방법

```jsx
<style jsx>{`
	/* 여기에 CSS를 기술한다. */
`}</style jsx>
```

### styled components 사용

→ className에 클래스를 지정하는 것이 아니라 스타일을 적용한 컴포넌트를 정의함

```jsx
import styled from "styled-components";

export const StyledComponents = () => {
    return (
        <SContainer>
            <STitle>styled components입니다</STitle>
            <SButton>버튼</SButton>
        </SContainer>
    );
};

const SContainer = styled.div`
    border: solid 1px #aaa;
    border-radius: 20px;
    padding: 8px;
    margin: 8px;
    display: flex;
    justify-content: space-around;
    align-items: center;
`;
const STitle = styled.p`
    margin: 0;
    color: #aaa;
`;
const SButton = styled.button`
    background-color: #ddd;
    border:none;
    padding: 8px;
    border-radius: 8px;
    &:hover {
        background-color: #aaa;
        color: #fff;
        cursor: pointer;
    }
`;
```


→ 맨 앞에 대문자 S를 부여한 이유는 나중에 코드를 봤을 때 styled components로 작성한 컴포넌트인지, 다른 외부 라이브러리를 사용한 컴포넌트인지를 알기 쉬게 하기 위함

### Emotion

→ 다양하게 사용할 수 있는 것이 특징

```jsx
/** @jsxImportSource @emotion/react */
import { jsx, css } from "@emotion/react";
import styled from "@emotion/styled";

export const Emotion = () => {
    // scss와 동일하게 작성 가능
    const containerStyle = css`
        border: solid 1px #aaa;
        border-radius: 20px;
        padding: 8px;
        margin: 8px;
        display: flex;
        justify-content: space-around;
        align-items: center;  
    `;

    // 인라인 스타일 작성 방법
    const titleStyle = css({
        margin: 0,
        color: "#aaa"
    });

    return (
        <div css={containerStyle}>
            <p css={titleStyle}>Emotion입니다</p>
            <SButton>버튼</SButton>
        </div>
    );
};

// styled-components 작성 방법
const SButton = styled.button`
    background-color: #ddd;
    border: none;
    padding: 8px;
    border-radius: 8px;
    &:hover {
        background-color: #aaa;
        color: #fff;
        cursor: pointer;
    }
`;
```

### Tailwind CSS

→ 이건 실습으로 진행

## Day 5 (재렌더링 구조와 최적화)

→ 재렌더링을 적절하게 제어하기 위해서는 언제 발생하는지 알아야 함

1. state가 업데이트된 컴포넌트
2. Props가 변경된 컴포넌트
3. 재렌더링된 컴포넌트 아래의 모든 컴포넌트

### 메모이제이션 | React.memo

→ 이전의 처리 결과를 저장해둠으로써 처리 속도를 높이는 기술

```jsx
import { useState, memo } from "react";

const Component = memo(() => {});
```

→ 컴포넌트를 괄호로 감싸면 해당 컴포넌트는 Props에 변경이 있을 때만 재렌더링됨
