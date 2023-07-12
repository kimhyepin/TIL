# JavaScript의 기본

## 구조

#### 1. 태그의 속성에 onclick을 넣어준다.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>www.button.com</title>
  </head>
  <body>
    <input type="button" value="night" onclick="" />
    <input type="button" value="day" onclick="" />

    <p>sme sw 부트캠프 2주차 강의입니다.</p>
  </body>
</html>
```

#### 2. onclick의 속성값으로 js 코드를 준다.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>www.button.com</title>
  </head>
  <body>
    <input
      type="button"
      value="night"
      onclick="
            document.querySelector('body').style.backgroundColor = 'black';
            document.querySelector('body').style.color = 'white';"
    />
    <input
      type="button"
      value="day"
      onclick="
            document.querySelector('body').style.backgroundColor = 'white';
            document.querySelector('body').style.color = 'black';"
    />

    <p>sme sw 부트캠프 2주차 강의입니다.</p>
  </body>
</html>
```

## 문법

#### 비교연산자

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title></title>
  </head>
  <body>
    <h1>Comparison operator & Boolean</h1>
    <h2>===</h2>
    <script>
      document.write(1 === 1);
      document.write(1 == 2);
      document.write(1 < 2);
      // 동등비교 연산자, 좌변과 우변 같으면 true, 아니면 false
      // true, false: boolean
    </script>
  </body>
</html>
```

#### 조건문

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title></title>
  </head>
  <body>
    <h1>Conditional statements</h1>
    <h2>Program</h2>
    <script>
      document.write("1<br>");
      document.write("2<br>");
      document.write("3<br>");
      document.write("4<br>");
    </script>

    <h2>IF-true</h2>
    <script>
      document.write("1<br>");
      if (true) {
        document.write("2<br>");
      } else {
        document.write("3<br>");
      }
      document.write("4<br>");
    </script>

    <!-- 실행결과 1,2,4 -->

    <h2>IF-false</h2>
    <script>
      document.write("1<br>");
      if (false) {
        document.write("2<br>");
      } else {
        document.write("3<br>");
      }
      document.write("4<br>");
    </script>

    <!-- 실행결과 1,3,4 -->
  </body>
</html>
```

#### 조건문의 활용

###### 이렇게 하면, 하나의 버튼으로 야간모드, 주간모드 모두 변경 가능

```html
<!-- 이전생략 -->
<input
  id="night_day"
  type="button"
  value="night"
  onclick="
if(document.querySelector('#night_day').value==='night')
{
   document.querySelector('body').style.backgroundColor='black';
   document.querySelector('body').style.color='white';
   document.querySelector('#night_day').value='day';
   } 

else 
{
   document.querySelector('body').style.backgroundColor='white';
   document.querySelector('body').style.color='black';
   document.querySelector('#night_day').value='night';
   } "
/>
<p>sme sw 부트캠프 2주차 강의입니다.</p>
<!-- 이후 생략 -->
```

#### this. 활용

###### this. 활용의 장점: 수많은 코드를 수정함에 있어서 불편함이 감소됨

```html
<input type="button" value="night" onclick="
var target = document.querySelector('body');
if(this.value == 'night') {
    target.style.backgroundColor = 'black'
    target.style.color='white'
    this.value='Day'
}
else{
    target.style.backgroundColor = 'white'
    target.style.color='black'
    this.value='Day'
}
">

<h1><a href="bootcamp.txt">WEB</a></h1>
<p>sme sw 부트캠프 2주차 강의입니다.</p>

<input type="button" value="night" onclick="
if(this.value==='night')
{
   document.querySelector('body').style.backgroundColor='black';
   document.querySelector('body').style.color='white';
   this.value='day';
   }
else
{
   document.querySelector('body').style.backgroundColor='white';
   document.querySelector('body').style.color='black';
   this.value='night';
   } ">

</body>
</html>
```

#### 배열 기초

```html
<!-- 배열관련
javascript array 라고 검색해보자 -->

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
  </head>
  <body>
    <h1>Array</h1>
    <h2>Syntax</h2>
    <script>
      var coworkers = ["hyebin", "egoing"];
    </script>

    <h2>get</h2>
    <script>
      document.write(coworkers[0]); // hyebin
      document.write(coworkers[1]); // egoing
    </script>

    <h2>add</h2>
    <script>
      coworkers.push("jenny");
      coworkers.push("Tom");
    </script>

    <h2>count</h2>
    <script>
      document.write(coworkers.length); //4 (hyebin, egoing, jenny, Tom)
    </script>
  </body>
</html>
```
