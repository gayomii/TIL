# #1. Variables

### const, let

---

- const

  :**read-only!** 

  한 번 선언한 값은 변경 할 수 없다.

\```{.javascript}

```javascript
const name = "gayeon"
name = "yeon" //error
```

(완벽하지 않은 read-only)

: object 내의 값은 변경이 가능하다.

```javascript
const person = { name: "gayeon" }
person.name = "Hi"
console.log(person) // { name: "Hi" }
```

- let

  : 기본적으로 const를 사용하고, 값을 변경해야 하는 변수는 let으로 선언해주기!

  

### features

___

- **temporal dead zone**

  javascript는 위에서부터 아래로 코드를 실행한다.

  ```javascript
  console.log(myName)
  var myName = "gayeon"
  
  // undefined 가 출력됨
  ```

  javascript의 hoisting속성 때문에 프로그램이 시작되면 variables가 제일 위로 가서 선언이 된다.

  따라서 위의 코드는 hoisting 때문에 undefined가 출력된다.

  ```javascript
  var myName
  console.log(myName)
  myName = "gayeon"
  ```

  실제론 error 가 발생해야 정상이지만 undefined가 실행되어 좋지 않은 코드가 실행되었다.

  **=> let과 const는 자바스크립트의 hoisting을 발생시키지 않게 한다.**

  ```javascript
  console.log(myName)
  let myName = "gayeon" 
  
  //error!
  ```



- **block scope**

  : block 안에서 선언한 변수는 안에서만 사용 가능! 외부에선 사용할 수 없다.

  ```javascript
  if(true) {
      let hello = "hi"
  }
  console.log(hello) //error
  ```

  외부에서 선언한 변수는 내부에서도 사용 가능하다.

  ```javascript
  let hello
  if(true) {
  	hello = "hahaha"
  }
  console.log(hello) //hahaha
  ```

  - let과 const는 **block scope** / var는 **function scope**

    ```javascript
    if(true) {
        var hello = "hi"
    }
    console.log(hello) // hi
    
    //var는 function scope이므로 if, else 등의 block 안에서 선언한 변수는 외부에서도 사용이 가능하다. (좋지 않은 코드!)
    ```

    ```javascript
    function a() {
        var hello = "hi"
    }
    console.log(hello) //error
    
    //function scope 이므로 function내부에서 선언한 var은 외부에서 사용 불가
    ```



##### 결론!! 어떠한 경우에서라도 var은 사용하지 않는 것이 좋다! let과 const를 사용하자!!



