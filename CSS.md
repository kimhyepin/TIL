# CSS의 기본

## 구조

#### 1. head에 style 태그 써줌

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <style>
      h2 {
        color: blue;
      }
    </style>
  </head>
  <body>
    <h2>Hello World!</h2>
  </body>
</html>
```

#### 2. 태그 옆에 style의 속성값 써줌
###### style의 속성값은 항상 css 코드로 작성하는 것이 약속된 바임

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
  </head>
  <body>
    <h1 style="color:red">Hello World!</h1>
  </body>
</html>
```

## 문법

```html
<html>
  <head>
    <meta charset="utf-8" />
    <style>
      ul li {
        color: red;
      }
      #lecture > li {
        border: 1px solid red;
        color: blue;
        /* 효과가 두개 이상이면, 세미콜론(;) 찍어주기 */
      }
      ul,
      ol {
        background-color: powderblue;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>

    <ol id="lecture">
      <li>HTML</li>
      <li>
        CSS
        <ol>
          <li>selector</li>
          <li>declaration</li>
        </ol>
      </li>
      <li>JavaScript</li>
    </ol>
  </body>
</html>
```

#### id값 선택: #사용

#### class값 선택: .사용

#### 태그 선택: 그냥 적어줌

#### CSS 선택자 우선순위: 아이디 선택자(ID selector) -> 클래스 선택자(Class selector) -> 태그 선택자(Element selector)

1. 태그전체 선택: 그냥 적어주기
   ex.
   <plate>선택원함</plate> 이면,

   ```html
   plate{
   <!-- CSS 코드 작성 -->
   }
   ```

2. 특정 id 선택: #이용
   ex. <apple id="big">선택원함</apple> 이면,

   ```html
   #big{
   <!-- CSS 코드 작성 -->
   }
   ```

3. 특성 class 선택: .이용
   ex. <orange class="small"> 선택원함 </orange> 이면,

   ```html
   .orange{
   <!-- CSS 코드 작성 -->
   }
   ```

span 선택자 vs div 선택자: CSS에서 다른 HTML 요소를 선택하기 위해 사용되는 두 가지 태그 선택자 (기능 X)
하지만, div 선택자는 단락을 나누고, span 선택자는 단락 나눔이 없음

<심화내용>

_: 모든 선택자 지칭
ex. plate 밑에 있는 모든 태그 선택?: plate _

A+B: A 옆에 인접한 B (A 선택안되고 B만 선택됨)  
A~B: A에 인접해있는 모든 B  
A>B: A의 직계자식을 선택  
A :first-child: 첫번째로 등장하는 A 선택  
: only-child: 누군가의 유일한 자식만 선택  
A : last-child: 마지막으로 등장하는 A 선택

그 외에도
:nth-child(A) :nth-last-child(A) :first-of-type :nth-of-type(A)
:nth-of-type(An+B) :only-of-type :last-of-type :empty :not(X)

이런게 있으니까 필요할 때 찾아보기 (생활코딩 다양한 선택자들 강의 참고)
