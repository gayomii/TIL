# #2. Functions

### arrow functions (화살표 함수)

---

```javascript
const names = ["lee", "ga", "yeon"]
const changeNames = names.map(function (name) {
    return `${name}!!`
})

console.log(changeNames) //["lee!!", "ga!!", "yeon!!"]
```

(* map함수: 배열 안의 item 하나하나 map안의 함수를 실행하는 함수이며, 함수는 return값이 존재해야 하며, map은 새로운 array를 반환한다.)

```javascript
//arrow function
const names = ["lee", "ga", "yeon"]
const changeNames = names.map(name => {
    return `${name}!!`
})

console.log(changeNames) //["lee!!", "ga!!", "yeon!!"]
```



- **implict return**

  : 한 줄에 적힌 코드를 return한다. { }를 추가하는 순간 implict return은 사라짐

```javascript
const names = ["lee", "ga", "yeon"]

//implict return 
const changeNames = names.map(name => `${name}!!`)
/* const changeNames = names.map(name => {
    return `${name}!!`
}) */

console.log(changeNames) //["lee!!", "ga!!", "yeon!!"]
```



- **"this" in Arrow functions**

기존 function

```html
<button>
    Click me
</button>
```

```javascript
const button = document.querySelector("button")
button.addEventListener("click", function() {
    console.log(this)
})

//<button>Click me</button>
```

arrow function의 this

```javascript
const button = document.querySelector("button")
button.addEventListener("click", () => {
    console.log(this)
})

//window ....
```

: arrow function은 this를 window object로 가지고 있다. 원하는 것을 가리키는 this를 사용하고 싶다면 기존의 function을 사용해야 한다.



- **array operation for arrow function**

  - find

    : 제공되는 조건을 만족하는 첫 번째 엘리먼트 값을 리턴하는 함수

    ```javascript
    const emails = ["honggildong@naver.com", "kimemployee@google.com", "gayeon@gmail.com", "leeemployee@google.com"]
    
    const foundMail = emails.find(item => item.includes("@google.com"))
    console.log(foundMail) // kimemployee@google.com
    ```

  - filter

    : 제공된 함수의 조건을 만족하는(true) 모든 엘리먼트로 새로운 array를 만든다.

    ```javascript
    const foundMail = emails.filter(item => item.includes("@google.com"))
    console.log(foundMail) // ["kimemployee@google.com", "leeemployee@google.com"]
    ```

  - forEach

    : 엘리먼트 하나씩 제공된 함수를 실행한다.

    ```javascript
    let name = []
    emails.forEach(item => {
        name.push(item.split("@")[0])
    })
    
    console.log(name)
    // ["honggildong", "kimemployee", "gayeon", "leeemployee"]
    ```

    (map 함수를 사용하면 새로운 배열을 return해주기 때문에 빈 배열을 선언하지 않아도 된다.)

    ```javascript
    emails.map( item => item.split("@")[0] )
    ```

    - Object Return

      ```javascript
      const cleaned = emails.map((item, index) => ({
      	username: item.split("@")[0],
          index // index: index
      }))
      
      // [{username: honggildong, index: 0}, ...]
      ```

  

- **default values**

  ```javascript
  function sayHi(name) {
      return `hello ${name}`
  }
  
  console.log(sayHi("gayeon")) //hello gayeon 
  console.log(sayHi()) //hello undefined
  ```

  argument를 선언하지 않으면 undefined가 출력됨.

  -> 이를 방지하기 위해 default values를 설정

  ```javascript
  function sayHi(name="abc") {
  	return `hello ${name}`
  }
  
  console.log(sayHi()) //hello abc
  ```

  ```javascript
  const sayHi = (name = "abc") => `hello ${name}`
  ```

  

