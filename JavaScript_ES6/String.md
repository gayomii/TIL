# #3. String

## Template Literals

: ES6의 새로운 문자열 표기법

‘ ' 또는" " 따옴표 문자 대신 **백틱(backtick)** 문자 **``**를 사용한다.



기존 문자열 선언 방법

```javascript
let name = "gayeon"
const sayHi = "Hello " + name + ", nice to meet you"

console.log(sayHi)
// Hello gayeon, nice to meet you
```

-> Template Literals 적용

```javascript
let name = "gayeon"
const sayHi = `Hello ${name}, nice to meet you`

console.log(sayHi)
// Hello gayeon, nice to meet you
```



### Features

---

- 여러줄의 문자열을 작성 가능

일반적인 ' ', " " 문자열은 여러줄 작성이 어려우나 ``문자열은 쉽게 작성이 가능하다.

```javascript
const template = `
	<div>
		<h1>Hello World</h1>
	</div
`;
```

javascript에서의 html 작성도 편리하다.

${ } 내부에서 변수, 수식 선언 가능

```javascript
const friends = ["lee", "kim", "dong"]

const list = `
	<h1>My Friends</h1>
	<ul>
		${friends.map(friend => `<li>${friend} </li>`).join('')}
	</ul>
`
```

- styled components

```javascript
const title = styled("h1")`
	background-color: red;
	color: blue;
`
```



## String method


- **includes()**

  : ( ) 안에 문자열이 포함된 문자열이 존재하면 true

  ```javascript
  const isEmail = email => email.includes('@')
  
  console.log(isEmail("gayeon@google.com")) //true
  ```

 
- **repeat()**

  : 원하는 어떤 글자든 반복할 수 있는 함수

  ```javascript
  const CC_NUM = "0000"
  const displayName = `${"*".repeat(5)}${CC_NUM}`
  console.log(displayName) //*****0000
  ```


- **startsWith(), endsWith() ** 

  : 해당 문자열로 시작하는지(끝나는지) 검사하는 함수

  이메일인지 (.com 으로 끝나는) 등을 확인 할 때 유용하다.

  ```javascript
  const name = "Ms. gayeon"
  console.log(name.startsWith("Ms")) //true
  console.log(name.endsWith("Ms")) //false
  ```

  
