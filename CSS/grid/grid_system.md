# grid system

: 1차원 레이아웃인 flex와 달리 행과 열의 2차원 레이아웃 시스템

###### (* grid system에 학습 할 땐 파이어폭스 브라우저 사용 권장)



### grid properties

---

부모 요소: **Grid Container**, 자식 요소: **Grid Item**

flex와 마찬가지로 부모 요소에 display: grid를 설정 해주면 부모 요소에서 설정한 스타일에 따라 grid item들이 배치된다.

- Grid Track : grid의 row 또는 column
- Grid Cell: grid의 한 칸을 가리킴

- Grid Line: 셀을 구분하는 선
- Grid Number: grid 라인의 각 번호
- Grid Gap: 셀 사이 간격
- Grid Area: 셀의 집합



### Grid Container

---

- **Grid 정의** (display)

```css
.container {
	display: grid;
}
```



- **grid-template-columns** : 열(column) 배치

`grid-template-columns: 1fr 1fr;` -> (fraction) 균일한 1: 1 비율인 2개의 column으로 배치하겠다는 것을 의미

```html
<body>
  <div class="container">
    <div>num1</div>
    <div>num2</div>
    <div>num3</div>
  </div>
</body>
```

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

<img width="494" alt="grid1" src="https://user-images.githubusercontent.com/52454824/92601280-963a6d00-f2e7-11ea-866b-8a19b1961c48.png">

repeat() 함수도 사용 가능하다.

```css
.container {
	width: 500px;
	grid-template-columns: 100px 100px 100px 100px 100px;
}
```

width가 500px인 container에 item 각각 100px씩 크기를 지정하고자 할 때, repeat() 을 사용하면 하나씩 입력하는 방법 보다 간소화하여 적용할 수 있다.

```css
.container {
	width: 500px;
	grid-template-columns: repeat(5, 100px);
}
```



- **grid-template-rows** : 행(row) 배치

고정적인 크기 단위도 사용 가능 (px)

```css
.container {
  display: grid;
  grid-template-rows: 100px 20px 50px;
}
```

<img width="495" alt="grid2" src="https://user-images.githubusercontent.com/52454824/92602273-e49c3b80-f2e8-11ea-9acb-abf1ce4f573e.png">



- **grid-gap** : 셀 간격 (grid-gap: [row-gap] [column-gap])

```css
grid-gap: 10px 20px;
```

<img width="497" alt="grid4" src="https://user-images.githubusercontent.com/52454824/92605004-2975a180-f2ec-11ea-8fd1-5c11cc9827ce.png">



- **align-content** : contents를 수직 정렬
- **justify-content** : contents를 수평 정렬
- **place-content** : align-content와 justify-content의 단축 속성으로 두 속성 모두에 적용됨

=> start, center, end, space-around, space-between, space-evenly, stretch 값 지정 가능



- **align-items** : items를 수직 정렬
- **justify-items** : items를 수평 정렬
- **place-items** 

=> start, center, end, stretch 값 지정 가능

xxx-content는 grid-container 자체 정렬이고, xxx-items는 item들 하나하나의 정렬이다.



### Grid Item

---

- **grid-template-areas**

```html
<body>
  <div class="container">
    <header>header</header>
    <main>main</main>
    <aside>aside</aside>
    <footer>footer</footer>
  </div>
</body>
```

```css
.container {
  display: grid;
  grid-template-rows: repeat(3, 100px);
  grid-template-columns: repeat(3, 1fr);
  grid-template-areas: 
    " header header header"
    " main main aside"
    " footer footer footer"
}

header { background-color: red; grid-area: header; }
main   { background-color: green; grid-area: main;   }
aside  { background-color: yellow; grid-area: aside;  }
footer { background-color: blue; grid-area: footer; }
```

<img width="496" alt="grid3" src="https://user-images.githubusercontent.com/52454824/92604549-989ec600-f2eb-11ea-9c06-d3003526483d.png">

