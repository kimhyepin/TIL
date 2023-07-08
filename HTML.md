# HTML의 기본

## 구조

#### <태그명></태그명> 여는태그, 닫히는 태그

#### 태그의 속성: 태그에 대한 추가 정보를 제공하는 요소

#### 속성은 태그에 대한 속성 이름과 속성 값으로 구성되며, 속성 값은 따옴표로 감싸줌 (속성이름="속성값")

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <!-- 여기서 meta가 태그, charset이 속성이름, utf-8이 속성값 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- 모바일 최적화를 위한 태그, 기계적으로 넣어주면 됨 -->
  </head>
  <body>
    <header>웹 상단부</header>
    웹 중반부
    <footer>웹 하단부</footer>
  </body>
</html>
```

---

## 자주 사용하는 태그

### 1. 제목태그

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  </head>
  <body>
    <h1>큰 제목</h1>
    <h2>작은 제목</h2>
    <h6>가장 작은 제목</h6>
  </body>
</html>
```

### 2. 줄바꿈태그

#### 1. br태그 (닫히는 태그 존재X)

#### 2. p태그 (닫히는 태그 존재O)

#### 두 태그의 공통점: 둘 다 줄바꿈 할때 사용되는 태그임

#### 두 태그의 차이점: 정해진 줄 바꿈간격이 있는 p태그와 달리 br태그는 한번쓰면 한번 띄워지고, 두번쓰면 두번 띄워지는 식으로 작동, 단락을 나눠줄때는 p태그를 사용해주는 게 더 좋음 (닫히는태그가 있기 때문에 한 단락임을 알아보기 유용)

### 3. 링크 태그

```html
<h1>오늘의 명언</h1>
우리 모두는 <strong>자신의 힘</strong>으로 발견한 내용을 가장 쉽게 익힌다. (<a
  href="https://ko.wikipedia.org/wiki/%EB%8F%84%EB%84%90%EB%93%9C_%EC%BB%A4%EB%88%84%EC%8A%A4"
  >도널드 커누스</a
>)
```

### 4. 목록태그

#### li태그 사이에 리스트 항목

#### 순서 있는 리스트의 경우: li태그를 ol태그로 감싸주기

#### 순서 없는 리스트의 경우: li태그를 ul태그로 감싸주기

```html
<!DOCTYPE html>
<html>
  <head>
    <title>HTML-수업소개</title>
    <meta charset="utf-8" />
  </head>

  <body>
    <h1><a href="index.html">HTML</a></h1>

    <ol>
      <li><a href="1.html">기술소개</a></li>
      <li><a href="2.html">기본문법</a></li>
      <li><a href="3.html">하이퍼텍스트와 속성</a></li>
      <li><a href="4.html">리스트와 태그의 중첩</a></li>
    </ol>
  </body>
  <html></html>
</html>
```

### 5. form 태그

#### 사용자가 입력한 정보를 서버로 전송할 때 사용하는 것

```html
<html>
  <body>
    <form action="http://localhost/login.php">
      <!-- <form></form>의 action 속성은 submit의 저장위치를 지정해주는 속성 
    이걸 해주면 제출 버튼을 눌렀을때 action의 속성값으로 서버가 이동함-->
      <p>아이디: <input type="text" name="id" /></p>
      <p>비밀번호: <input type="password" name="pass" /></p>
      <p>주소: <input type="text" name="address" /></p>
      <input type="submit" />
    </form>
  </body>
</html>
```

````html
<html>
  <head>
    <meta charset="utf-8" />
  </head>
  <body>
    <form action="http://localhost/form.php">
      <input type="submit" value="전송" />
      <input type="button" value="버튼" onclick="alert('hello world')" />
      <input type="reset" />
      <!-- type button vs type submit
        버튼은 그냥 단순히 눌러지기만 함
        제출은 사이트가 바뀌면서 제출됨  -->
    </form>
  </body>
</html>
```html
<html>
  <head>
    <meta charset="utf-8" />
    <body>
      <form action="http://localhost/color.php">
        <h1>색상</h1>
        <select name="color">
          <option value="red">붉은색</option>
          <option value="black">검은색</option>
          <option value="blue">파란색</option>
          <!-- <option></option>태그의 value속성은 사용자가 각각 붉은색, 검은색, 파란색을 선택했을때
            컴퓨터가 red, black, blue로 저장해서 기억하게 함 -->
        </select>
        <h1>색상(다중선택)</h1>
        <select name="color2" multiple>
          <!-- multiple이라는 속성은 사용자가 여러개 항목 선택할 수 있음 -->
          <option value="red">붉은색</option>
          <option value="black">검은색</option>
          <option value="blue">파란색</option>
          <!-- <option></option>태그의 value속성은 사용자가 각각 붉은색, 검은색, 파란색을 선택했을때
            컴퓨터가 red, black, blue로 저장해서 기억하게 함 -->
        </select>
        <input type="submit" />
      </form>
    </body>
  </head>
</html>

<!-- 이거 실행시키면 http://localhost/color.php?color=red&color2=black&color2=blue 라는 url로 연결됨 
color1에 처음 선택한 선택지 저장, color2에 두번째 선택한 선택지 저장-->
````

```html
<html>
  <head>
    <meta charset="utf-8" />
    <body>
      <form action="http://localhost/order.php">
        <h1>색상</h1>
        <p>
          붉은색: <input type="radio" name="color" /> 검은색:
          <input type="radio" name="color" checked />
          <!-- checked속성은 기본 선택값 지정해줄때 이용 -->
          파란색: <input type="radio" name="color" />
        </p>
        <!-- radio 값 특징: 같은 이름으로 지정되어 있으면 다중선택 안되고 하나만 선택됨 -->
        <h1>사이즈(다중선택)</h1>
        <p>
          95: <input type="checkbox" name="size" value="95" /> 100:
          <input type="checkbox" name="size" value="100" /> 105:
          <input type="checkbox" name="size" value="105" />
          <!-- checkbox: 같은 이름으로 지정되어 있으면서도, 다중선택할 수 있는 것  -->
        </p>
        <input type="submit" />
      </form>
    </body>
  </head>
</html>
```

```html
<html>
  <head>
    <meta charset="utf-8" />
  </head>
  <body>
    <form
      action="http://localhost/upload/php"
      method="post"
      enctype="multipart/form-data"
    >
      <input type="file" name="profile" />
      <!-- type이 file인게 하나라도 있으면 무조건 method="post" enctype="multipart/form-data"
               이라는거 form의 속성값으로 지정해줘야됨 -->
      <input type="submit" />
    </form>
  </body>
</html>
```

```html
<html>
  <head>
    <meta charset="utf-8" />
    <body>
      <form action="http://localhost/hidden.php">
        <input type="text" name="id" />
        <input type="hidden" name="hide" value="egoing" />
        <!-- hidden은 화면상에 보이진않지만 제출시 url에 hide=egoing이라는 값이 전송되어 있음을 url을 통해 확인해볼 수 있음 
                ui가 없지만, url에 무언가를 전송하고 싶을때는 type에 hidden주면 됨-->
        <input type="submit" />
      </form>
    </body>
  </head>
</html>
```

```html
<html>
  <body>
    <form action="">
      <p>
        <label for="id_txt">text</label>:
        <!-- <label></label>는 text가 어떠한 정보의 이름표다(?)라는 것을 좀 더 직관적으로 나타낼 수 있는 태그 -->
        <!-- 어떠한 정보가 무엇인지 구체적으로 알려주는 속성=for -->
        <input id="id_txt" type="text" name="id" value="default value" />
      </p>
      <p>
        <label for="password">password</label>:
        <input id="password" type="password" name="pwd" value="default value" />
      </p>
      <!-- 이렇게 for로 지정해주면 커서 위치가~ -->
      <p>
        <label for="textarea">textarea</label>:
        <textarea id="textarea" cols="50" rows="2">default value</textarea>
      </p>
      <p>
        <label>
          <input type="checkbox" name="color" value="red" /> 붉은색
        </label>
        <!-- label로 묶어주면 label을 클릭하고 checkbox를 클릭하지 않아도 
                checkbox에 클릭이 자동으로됨 -->
      </p>
      <p>
        <label for="color_blue">
          <input id="color_blue" type="checkbox" name="color" value="blue" />
          파란색
          <!-- 위에있는 붉은색 checkbox와 코드는 다르지만, 완전히 같은 의미의 코드임 -->
        </label>
      </p>
    </form>
  </body>
</html>
```

```html
<html>
  <head>
    <meta charset="utf-8" />
    <body>
      <form action="http://localhost/method.php" method="post">
        <input type="text" name="id" />
        <!-- <input type="password" name="pwd"> -->
        <!-- 이렇게하면 url에 비밀번호 노출된다는 문제점이 있음
                url에 감춰서 전달해야 하는 정보가 있음: method="post로 해결
                기본은 method="get"으로 지정되어 있어서 url로 데이터가 전송되어 있음 -->
        <input type="submit" />
      </form>
    </body>
  </head>
</html>
```

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
  </head>
  <body>
    <form action="login.php" autocomplete="on"></form>
    <!-- autocomplete="on" 내가 예전에 입력했던 정보를 브라우저가 기억하고 있다가 자동완성 시켜줌 -->

    아이디: <input type="text" name="id" autofocus />
    <!-- autofocus를 설정해주면 웹페이지를 열었을때 커서가 아이디를 입력하는 창에 기본으로 가 있음 -->

    <!-- <input type="text" name="id" placeholder="아이디를 입력해주세요"> 
        이렇게해주면 입력 field에 아이디를 입력해주세요라는 메세지 나옴 -->
    비밀번호: <input type="password" name="password" autocomplete="off" />
    <!-- autocomplete="off": password는 자동완성 비활성화  -->

    <input type="submit" />
  </body>
</html>
```

```html
<html>
  <head>
    <meta charset="utf-8" />
  </head>
  <body>
    <form action="register.php">
      <input
        type="text"
        name="id"
        placeholder="아이디를 입력해주세요"
        required
        pattern="[a-zA-z].+[0-9]"
      />
      <input type="email" name="email" placeholder="이메일 입력" />
      <!-- required 속성은 무조건 입력해야 되는 
            required pattern의 속성값은 정규표현식이여야만 한다.
            형식을 지정해줄 수 있음 -->
      <input type="submit" />
    </form>
  </body>
</html>
```

### 6. 이미지 태그

#### 동작법: img라는 이름의 태그를 만나면 웹브라우저는 어떻게 작동하는 것일까?

#### img.jpg라는 파일이 있는 웹서버에 접속해서 해당 jpg파일 다운 받은 다음에 웹 사이트에 가져다 붙히는 식으로 작동함

#### 사진을 많이 가져다 붙혀서 웹사이트가 지연됐을때 무슨 사진이 잘못된건지 알아내기는 매우 까다로움 (그럴때 우리를 도와줄 수 있는 도구가 "network" 도구)

```html
<html>
  <body>
    <img src="img.jpg" width="100" alt="산이미지" title="산 이미지" />
  </body>
</html>

<!-- width는 폭지정, height는 높이지정
img src="링크" 하면 이미지 삽입가능
만약 폭이나 높이 둘 중에 하나만 지정해놓으면 변경된 폭에 따라 높이 자동변경 or 높이에 따라 폭 자동변경
alt = "어쩌고" 하면 이미지가 깨졌을때, 위에 어쩌고 라고 설명이 뜸, alternative text의 약자 (시각장애인 접근, 검색엔진 걸림 등의 장점있기 때문에 꼭 써주는게 좋음 -->
```

### 7. 테이블 태그

#### 표(?) 만들고 싶을 때 사용해줌

#### border속성은, 테이블의 테두리 만들어주는 속성 (1로 지정하면 얇은 테두리, 2로 지정하면 두꺼운 테두리)

#### 각각의 데이터 <td></td> 로 묶어주고같은 행에 있는 데이터 <tr></tr>로 묶어줌 그리고 전체 테이블 <table></table>로 묶어줌 그리고 table의 속성 border를 지정해줌

#### rowspan속성 : row는 세로행 의미, (본 코드에서는) 2개의 행 합쳐짐 [표 병합 - 수직]

#### colspan속성 : column은 가로열 의미, (본 코드에서는) 3개의 열 합쳐짐 [표 병합 - 수평]

```html
<html>
  <body>
    <table border="2">
      <thead>
        <tr>
          <th>이름</th>
          <th>성별</th>
          <th>주소</th>
          <th>회비</th>
          <!-- 물론 td로 묶어도 되지만, 이러면 이름 성별 주소가 진하게 표시돼서 가독성이 좋아짐 -->
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>최진혁</td>
          <td>남자</td>
          <td rowspan="2">청주</td>
          <td>1000</td>
        </tr>
        <tr>
          <td>최유빈</td>
          <td>여자</td>
          <td>500</td>
        </tr>
      </tbody>
      <tfoot>
        <td colspan="3">합계</td>
        <td>1500</td>
      </tfoot>
      <!-- tfoot은 항상 코드 제일 밑에 써지고, thead는 가장 위에, tbody는 중간에 써짐 -->
    </table>
  </body>
</html>
```

### 8. meta 태그

#### 인코딩 (정보들을 저장: 인코딩, 저장되어 있는 정보를 화면에 꺼내서 표시: 디코딩)

#### meta 태그로 웹의 내용이 달라지진 않지만, 정보의 관점에서 달라짐

```html
<html>
  <head>
    <meta charset="utf-8" />
    <!-- 이 웹페이지가 utf-8 이라는 방법을 통해서 저장되었음을 알려주는 코드-->
    <meta name="description" content="생활코딩의 소개자료" />
    <!-- 웹에 표시되지는 않음, 이게 뭐하는 코드인지 간략하게 설명해주는 meta tag -->
    <meta
      name="keywords"
      content="코딩, coding, 생활코딩, 프로그램, html, css, javascript"
    />
    <meta name="author" content="egoing" />
    <meta http-equiv="refresh" content="30" />
    <!-- 이 웹페이지는 30초 간격으로 refresh가됨 -->
  </head>
  <body>
    생활코딩은 일반인들에게 프로그래밍을 알려주는 온라인/오프라인 강의입니다.
  </body>
</html>
```

### 9. semantic 태그

#### 의미론적인 태그

```html
<!DOCTYPE html>
<html>
    <head>
        <title>HTML-수업소개</title>
        <meta charset="utf-8">
    </head>

    <body>
        <header>
            <h1><a href="index.html">HTML</a></h1>
        </header>
    <!-- header 태그는 시각적인 기능은 없음
    단, 그냥 코드를 봤을 때 이 부분이 가장 큰 의미를 가지는 부분이다~ 하는 것을 알려주기 위해 추가적으로 작성한 코드임 -->
    <nav>
        <section>
        <ol>
	        <li><a href="1.html">기술소개</a></li>
            <li><a href="2.html">기본문법</a></li>
            <li><a href="3.html">하이퍼텍스트와 속성</a></li>
            <li><a href="4.html">리스트와 태그의 중첩</a></li>
        </ol>
    </nav>
    <!-- nav태그는 이 웹 페이지를 탐색할 때~ -->

    <article>
    </section>
        <!-- 역할이 불분명한 부분은 section으로 묶어주기 -->
        <h2>선행학습</h2>
            본 수업을 효과적으로 수행하기 위해서는 웹애플리케이션에 대한 전반적인 이해가 필요합니다. 이를 위해서 준비된 수업은 아래 링크를 통해서 접근하실 수 있습니다.
    </article>
    <!-- <article></article> 태그는 본 웹페이지의 본문 부분을 드러내는 태그 -->

        <footer>
            <ul>
            <li><a href="privacy.html">개인정보정책</a></li>
            <li><a herf="about.html">회사소개</a></li>
            </ul>
        </footer>
    </body>
<html>
```

### 10. 퇴출된 태그 (font)

#### html의 본질: 정보전달

#### css의 본질: 디자인

````html
<html>
  <head>
    <meta charset="utf-8" />
  </head>
  <body>
    <font size="1" color="red">Hello</font> world
    <!-- font는 대표적인 퇴출당한 태그임 
        왜? 코드가 너무 복잡해져서,, css 그래서 고안함 
        html은 정보이다-->
  </body>
</html>
```
````
