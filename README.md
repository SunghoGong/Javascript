# 모던 자바스크립트로 배우는 리액트 입문(한빛미디어, 2022)

## Modern Javascript

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

console.log(fee2);
```

→ 논리 연산자 &&은 **왼쪽을 true로 판정하면 오른쪽을 반환**(||과 반대)

### falsy, truthy, nullish

→ 암묵적으로 true로 변환되는 값을 truthy, false로 변환되는 값을 falsy라고 부름

→ 0이나 “”(빈 문자)는 falsy, [ ](빈 배열)이나 { }(빈 객체)는 truthy임

→ null과 undefined로 판정되는 것은 nullish라고 부름
