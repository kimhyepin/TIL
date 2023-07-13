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
#### 반복문 기초

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
  </head>
  <body>
    <h1>Loop</h1>
    <ul>
      <script>
        document.write("<li>1</li>");
        var i = 0;
        while (i < 3) {
          document.write("<li>2</li>");
          document.write("<li>3</li>");
          i += 1;
        }
        document.write("<li>4</li>");
      </script>
    </ul>
  </body>
</html>
```

#### 배열과 반복문의 결합

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
    </head>
    <body>
        <h1>Loop & Array </h1>
        <script>
            var coworkers= ['egoing', 'leezche', 'duru', 'taeho', 'jenny'];
            var i = 0
            while(i < coworkers.length) {
                // coworkers 의 수가 바뀌더라도 유연성있게
            document.write('<li>'+coworkers[i]+'</li>')
            i+=1
            }
        </script>
        <!-- <h2>coworkers</h2>
        <ul>
            <li>egoing</li>
            <li>leezche</li>
            <li>duru</li>
            <li>taeho</li>

        우리가 궁극적으로 하고 싶은건 이거, 이거를 좀 더 일반화해서 반복문으로 만든게 저 위에 것임
        배열: 순서대로 데이터를 하나에 담는거
        반복문: 순서대로 잘 담긴 배열을 이용해서 순차적으로 꺼내게 할 수 있음-->
        </ul>
    </body>
</html>
```

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
  </head>
  <body>
    <h1><a href="web.html">WEB</a></h1>
    <h2><a href="JavaScript.html">JS</a></h2>
    <input
      type="button"
      value="night"
      onclick="

    if(this.value==='night')
    {
    document.querySelector('body').style.backgroundColor='black';
    document.querySelector('body').style.color='white';
    this.value='day';

    var alist = document.querySelectorAll ('a');
    // a태그 전체 가져오기
    var i = 0;
        while(i<alist.length) {
            alist[i].style.color= 'powderblue';
            i+=1;
        }
    } 

    else 
    {
    document.querySelector('body').style.backgroundColor='white';
    document.querySelector('body').style.color='black';
    this.value='night';

    var alist = document.querySelectorAll ('a');
    var i = 0;
        while(i<alist.length) {
            alist[i].style.color= 'blue';
            i+=1;
        }
    } 
    
    "
    />
  </body>
</html>
```

#### 함수기초

```html
<!DOCTYPE html>
<html>
  <head>
    <body>
      <h1>Funcion</h1>
      <h2>Basic</h2>
      <ul>
        <script>
          function two() {
            document.write("<li>2-1</li>");
            document.write("<li>2-2</li>"); // 재사용하고 싶은 코드 적어주기
          }
          document.write("<li>1</li>");
          two();
          document.write("<li>3</li>");
          two();
        </script>
      </ul>
      <h2>Parameter & Argument</h2>
      <script>
        function onePlusOne() {
          document.write(1 + 1 + "<br>");
        }
        onePlusOne();

        // 함수가 입력값에 따라 다른 결과를 출력?
        // ex. sum(2,3); (5출력) sum (3,4); (7출력) 하는법?

        function sum(left, right) {
          // 괄호안의 값: 매개변수 (값을 받아서 함수 안으로 매개해주는 변수)
          document.write(left + right + "<br>");
        }
        sum(2, 3);
        sum(3, 4);
      </script>
      <h2>Return</h2>
      <script>
        function sum2(left, right) {
          return left + right;
        }
        document.write(sum2(2, 3) + "<br>");
        document.write('<div style="color:red">' + sum2(2, 3) + "</div>");
        document.write('<div style="font-size: 3rem">' + sum2(2, 3) + "</div>");
      </script>
    </body>
  </head>
</html>
```

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <script>
      function toggleColor() {
        var body = document.querySelector("body");
        var alist = document.querySelectorAll("a");

        if (body.style.backgroundColor === "black") {
          body.style.backgroundColor = "white";
          body.style.color = "black";
          this.value = "night";
          var i = 0;
          while (i < alist.length) {
            alist[i].style.color = "blue";
            i += 1;
          }
        } else {
          body.style.backgroundColor = "black";
          body.style.color = "white";
          this.value = "day";
          var i = 0;
          while (i < alist.length) {
            alist[i].style.color = "powderblue";
            i += 1;
          }
        }
      }
    </script>
  </head>
  <body>
    <h1><a href="web.html">WEB</a></h1>
    <h2><a href="JavaScript.html">JS</a></h2>
    <input type="button" value="night" onclick="toggleColor.call(this)" />
    <h3>sme 부트캠프 강의입니다.</h3>
    <input type="button" value="night" onclick="toggleColor.call(this)" />
  </body>
</html>
<!-- 
위의 코드에서 toggleColor라는 함수를 정의함. 이 함수는 배경색, 텍스트 색상 및 링크 색상을 토글하는 역할을 함. onclick 속성에서 toggleColor.call(this)를 호출하여 함수를 실행시킴. call(this)를 사용하면 클릭한 요소에 대한 this 컨텍스트를 함수로 전달할 수 있음.

이렇게 변경한 코드는 중복 코드를 줄이고 코드의 유지 관리와 가독성을 향상시킴.. 이제 버튼을 클릭할 때마다 배경색, 텍스트 색상 및 링크 색상이 토글됨. -->
```

