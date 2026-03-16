# Javascript 실습(모던 자바스크립트로 배우는 리액트 입문, 한빛미디어)

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
