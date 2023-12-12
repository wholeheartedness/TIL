# JavaScript 기초



1. HTML에서 작성

- <body> </body> 사이에 작성합니다

- '<script> </script> 사이에 작성합니다

  -  documnet.write (' 원하는 출력 ')

  

2. js에서 작성 

- <body> </body> 사이에 작성합니다

- '<script> </script> 사이에 작성합니다

  -  <script src = '파일경로.js'> </script>

  - 파일경로 안에 있는 js 파일 실행 

---

- 변수 선언은 아래와 같이 합니다

  - `var 변수명 = 값`;
    - var name = '이구월';
    - var 나이 = 3;
  - let 변수명 = 값;
  - const 변수명 = 값;

  <br>

  

- `typeof` : 해당 데이터가 어떤 타입인지 확인할 수 있습니다

  - String, number...

    ![image-20231211092829281](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231211092829281.png)

<br>



- `Math.random();` : 0 이상 1미만 실수 (float)를 랜덤으로 생상합니다
- `parseInt();` : 소수점은 버리고 정수로 변환합니다

---

- 배열

  - var 변수명 = [1,2,3,4,5,...];
    - 변수명[0] == 1

- `.push(값);` : 배열의 마지막에 값 추가합니다

- `.indexOf(값);` : 배열 내에 값이 있으면 위치, 없으면 -1을 반환합니다

  - 중복없는 로또번호 추출기를 만들어보겠습니다.

    ```js
    var lotto = [];
    for (var i = 0; i < 6; i++){
        var num = parseInt(Math.random() * 45 + 1);
        if (lotto.indexOf(num) == -1) {
            lotto.push(num);
        }
    }
    document.write(lotto);
    ```

    <br>

- `.length();` : 배열의 길이를 반환합니다

- `.sort()` : 맨 앞자리를 기준으로 정렬 합니다 (ex. 1, 11, 2, 22, 3, 33)

  - `.sort((a,b) => a-b)` : 오름차순으로 정렬합니다

  - 로또번호 추출기 웹페이지를 만들어보겠습니다.

    ```js
    <h1>로또 번호 추첨기</h1>
    <script>
        var lotto = [];
        while (lotto.length < 6) {
            var num = parseInt(Math.random() * 45 + 1);
            if (lotto.indexOf(num) == -1) {
                lotto.push(num);
            }
        }
        lotto.sort((a,b)=>a-b);
        document.write("<div class='ball ball1'>" + lotto[0] + "</div>");
        document.write("<div class='ball ball2'>" + lotto[1] + "</div>");
        document.write("<div class='ball ball3'>" + lotto[2] + "</div>");
        document.write("<div class='ball ball4'>" + lotto[3] + "</div>");
        document.write("<div class='ball ball5'>" + lotto[4] + "</div>");
        document.write("<div class='ball ball6'>" + lotto[5] + "</div>");
    </script>
    ```

    ```css
    .ball {
        float: left;
        width: 60px;
        height: 60px;
        line-height: 60px;
        font-size: 28px;
        border-radius: 100%;
        text-align: center;
        vertical-align: middle;
        color: #fff;
        font-weight: 500;
        text-shadow: 0px 0px 3px rgba(73, 57, 0, .8);
        margin-right: 6px;
    }
    
    .ball1 {
        background: #fbc400;
    }
    .ball2 {
        background: #69c8f2;
    }
    .ball3 {
        background: #ff7272;
    }
    .ball4 {
        background: #aaa;
    }
    .ball5 {
        background: #b0d840;
    }
    .ball6 {
        background: #c7c7c7;
    }
    
    ```

    <br>

    <br>

    <br>

---

## 2. Documnet Object Model

![DOM | PoiemaWeb](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/traversing.png)

![문서 객체 모델 DOM 과 자바스크립트 JavaScriptㅣ생성 방식 및 접근 방법 - 코드스테이츠 공식 블로그](https://i0.wp.com/blog.codestates.com/wp-content/uploads/2022/12/문서-객체-모델-DOM-과-자바스크립트-JavaScript.jpg?resize=750%2C478&ssl=1)

- DOM : 문서 객체 모델입니다
  - 웹페이지의 콘텐츠, 구조, 스타일 요소를 구조화시켜 표현하는 모델입니다.
  - 프로그래밍 언어가 해당 문서에 접근할 수 있는 API를 제공합니다
  - 일종의 인터페이스입니다.

<br>

- `document.getElementById('요소ID').value` : ID가 부여된 요소 값을 가져옵니다.

  ```
  <body class="container">
      <h1>이구월</h1>
      <textarea class="form-control" rows="3" id="september">이구월은 매우매우 귀여운 고냥이입니다😺.</textarea>
      <script>
          var content = document.getElementById('september').value;
      </script>
  </body>
  ```

  <br>

- `span` : html내 여러 태그들을 묶어주는 주머니 입니다(p, div와 유사합니다)

  ![img](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/span.png)

  - p, div, span의 차이점은 아래의 문서를 참고합니다.

    ![image-20231211102844643](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231211102844643.png)

    출처 : https://m.blog.naver.com/juyoung1704/221632845422

<br>

- `innerHTML= " "` : HTML 요소에 접근하여 A를 B로 바꾸어서 출력합니다.

  ```html
  document.getElementById('age').innerHTML = "4살"
  ```

<br>

- 함수 선언은 아래와 같이 합니다.

  - `function 함수명() { 명령어 }; `

  

  <br>

  <br>

  <br>

---

## 3. 이벤트

- 마우스 클릭, 키보드 누름, 값 변화, 페이지 로딩 등

- 사용자가 웹 브라우저에서 취하는 모든 동작에 대한 행동을 말합니다.

  ![image-20231211104716293](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231211104716293.png)

  출처 : https://velog.io/@bami/Javascript-%EC%9D%B4%EB%B2%A4%ED%8A%B8

  - 이벤트 핸들링 : 이벤트가 발생할때 특정한 동작을 수행합니다

  - `이벤트 = 이벤트 핸들링`

    ```html
     <textarea onkeydown='counter();' ....>
    ```

    - 키를 눌렀을 때 counter 함수가 실행됨



<br>

- `substring(자를 범위 가장 앞 index, 가장 뒤 index)`  : string 문자를 범위를 지정하여 자릅니다.

  - var 한글 = 가나다라 마바사 abcd 

    => 한글.substring(0,8) == 가나다라 마바

  - 띄어쓰기 포함입니다.

    <br>

    <br>

    <br>

    

---

## 4. J-Query

- 자바스크립트를 쉽게 사용할 수 있는 라이브러리입니다
- 자주 사용하는 메소드는 아래와 같습니다
  - https://code.tutsplus.com/20-helpful-jquery-methods-you-should-be-using--net-10521t

<br>

<br>

### 4.1. 제이쿼리 사용하기

- 제이쿼리 사이트에 접속합니다

  - https://releases.jquery.com/jquery/

- 가장 최신 버전의 jQuery Core의 minified를 클릭합니다

  ![image-20231211112653653](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231211112653653.png)

- 소스코드를 복사하여 사용할 코드에 붙여넣습니다.

  ![image-20231211112732569](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231211112732569.png)

  ```html
  <!DOCTYPE html>
  <html lang="ko">
  <head>
      <meta charset="UTF-8">
      <title>jQuery 기초</title>
  </head>
  <body>
      <h1>jQuery 기초</h1>
      <textarea id="content">jQuery를 배워보자</textarea>
      <script
      src="https://code.jquery.com/jquery-3.5.1.js"
      integrity="sha256-QWo7LDvxbWT2tbbQ97B53yJnYU3WhH/C8ycbRAkjPDc="
      crossorigin="anonymous"></script>
      <script>
          $('#content').val()
      </script>
  </body>
  </html>
  ```

  

- 이제 제이쿼리를 사용할 수 있습니다.

  <br>

  <br>

### 4.2. 제이쿼리 문법

- `$(선택자). 동작함수();` : $는 제이쿼리를 의미합니다.

  - $() 함수는 선택자에 의해 선택된 요소들을 jQuery 객체로 반환합니다.

  <br>

  #### 1. 선택기 : HTML  요소를 선택하고 조작합니다.

  - `$("p")` : 요소 선택기 (요소 이름 기반)
  - `$("#test")` : id 선택기
  - `$(".test")` : class 선택
    <br>

  #### 2. 이벤트 : 웹페이지가 응답할 수 있는 다양한 작업을 말합니다.

  - 🖱️**2-1. 마우스 이벤트**

    - 주요 메서드

      | .click()        | 자바스크립트의 "click" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "click" 이벤트를 발생시킴. |
      | --------------- | ------------------------------------------------------------ |
      | **.dblclick()** | 자바스크립트의 "dblclick" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "dblclick" 이벤트를 발생시킴. |
      | **.hover()**    | 자바스크립트의 "mouseenter"와 "mouseleave" 이벤트를 같이 인벤트 핸들러와 연결함. |
      | .mousedown()      | 자바스크립트의 "mousedown" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "mousedown" 이벤트를 발생시킴. |
      | ----------------- | ------------------------------------------------------------ |
      | **.mouseenter()** | 해당 요소 위로 마우스가 진입할 때 발생하는 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 마우스 진입 이벤트를 발생시킴. |
      | **.mouseleave()** | 해당 요소에서 마우스가 빠져나갈 때 발생하는 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 마우스가 빠져나가는 이벤트를 발생시킴. |
      | **.mousemove()**  | 자바스크립트의 "mousemove" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "mousemove" 이벤트를 발생시킴. |
      | **.mouseout()**   | 자바스크립트의 "mouseout" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "mouseout" 이벤트를 발생시킴. |
      | **.mouseover()**  | 자바스크립트의 "mouseover" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "mouseover" 이벤트를 발생시킴. |
      | **.mouseup()**    | 자바스크립트의 "mouseup" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "mouseup" 이벤트를 발생시킴. |

    <br>

    

  - **⌨️2-2. 키보드 이벤트**

    - 주요 메서드

      | .keydown()      | 자바스크립트의 "keydown" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "keydown" 이벤트를 발생시킴. |
      | --------------- | ------------------------------------------------------------ |
      | **.keyup()**    | 자바스크립트의 "keyup" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "keyup" 이벤트를 발생시킴. |
      | **.keypress()** | 자바스크립트의 "keypress" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "keypress" 이벤트를 발생시킴. |

    

  - **2-3. 입력 양식(form)이벤트**

    - 주요 메서드

      | .blur()         | 자바스크립트의 "blur" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "blur" 이벤트를 발생시킴. |
      | --------------- | ------------------------------------------------------------ |
      | **.change()**   | 자바스크립트의 "change" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "change" 이벤트를 발생시킴. |
      | **.select()**   | 자바스크립트의 "select" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "select" 이벤트를 발생시킴. |
      | **.submit()**   | 자바스크립트의 "submit" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "submit" 이벤트를 발생시킴. |
      | **.focus()**    | 자바스크립트의 "focus" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "focus" 이벤트를 발생시킴. |
      | **.focusin()**  | "focusin" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "focusin" 이벤트를 발생시킴. |
      | **.focusout()** | "focusout" 이벤트와 이벤트 핸들러를 연결하거나, 해당 요소에 "focusout" 이벤트를 발생시킴. |

  <br>

- 아래의 html 문법을

  ```
   <button id="click" onclick="hello();">클릭</button>
  ```

  <br>

- jQuery 문법으로 나타내면 아래와 같습니다.

  ```
  $('#click').click(hello);
  ```

  

---

## 5. 익명함수

- 함수를 정의하지 않고 작성하는 함수입니다.

  ```html
  $('#click').click(function() {
  	console.log("익명함수 사용 예시");
  });
  ```

  <br>

  <br>

## 6. 메서드 사용하기

- 사용하고 싶은 메서드는 `jquery 나타나기` 와 같이 구글에 검색하여 사용합니다.

  ![image-20231211132201219](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231211132201219.png)

<br>

- 예시로 애니메이션 효과를 주는 .animate() 메서드를 사용해보겠습니다.

  ```html
  .animate( properties [, duration ] [, easing ] [, complete ] )
  ```

  - `properties ` : 애니메이션 효과를 줄 속성입니다.

  - `duration` : 애니메이션 효과 완료시까지 걸리는 시간 입니다

  - `easing` : 애니메이션 효과의 방식입니다 (swing or linear)

  - `complete` : 요소가 사라진 후 수행할 작업 입니다.

    ```html
    $('#drone').click(function(){
        $('#spit').fadeIn();
        $('#spit').animate({left: '+=250'});
    });
    ```

    

<br>

- CallBack 함수 활용 

  - 함수가 complete된 후 다음 함수를 실행할 수 있습니다.

  - 함수안에 complete 후 실행할 함수를 작성합니다.

    ```html
    <script>
        var hp = 3;
       $('#drone').click(function() {
           $('#spit').fadeIn();
           $('#spit').animate({'left': '+=180'});
           $('#spit').fadeOut( function() {
               hp -= 1;
               $('#hp').text('HP :' + hp);
               if (hp == 0) {
                   $('#bunker').fadeOut();
               }
           })
           $('#spit').css({'left' : '150px'})
       })
    </script>
    ```

    <br>

    <br>

    <br>

---

## 7. 객체 (Object)

- 데이터를 담는 상자를 말합니다.

- 내장 객체 : 자바스크립트 자체에서 제공하는 객체

- Date 객체를 살펴보겠습니다.

  - MDN 문서 내에 다양한 메서드를 살펴볼 수 있습니다.
  - https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Date

  <img src="https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231211141515983.png" alt="image-20231211141515983" style="zoom: 67%;" />

  

  <img src="https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231211141540488.png" alt="image-20231211141540488" style="zoom: 80%;" />

<br>

- 기념일 계산기 실습을 통해 알아보겠습니다.

  ```html
  </head>
  <body class="container">
      <section class='photos'>1
          <img id='seoju' src="seoju.jpeg" alt="duhee">
          <img id='heart' src="heart.png" alt="heart">
          <img id='september' src="september.jpeg" alt="jisook">
      </section>
      <div class='container d-flex flex-column justify-content-center align-items-center mt-3'>
          <h3>서주♥구월</h3>
          <h3 id='love'>0일째</h3>
          <h4 class="date">2022.1.9</h4>
      </div>
      <hr/>
      <section class='special-day'>
          <h3 class='title'>크리스마스</h3>
          <div class='date-box'>
              <p id='christmas' class='days-left'>0일 남음</p>
              <p class='date'>2023.12.25</p>
          </div>
      </section>
      <hr/>
      <hr/>
      <section class='special-day'>
          <h3 class='title'>1000일</h3>
          <div class='date-box'>
              <p id='thousand' class='days-left'>0일 남음</p>
              <p id='thousand-date' class='date'>0000.00.00</p>
          </div>
      </section>
      <hr/>
      <script
    src="https://code.jquery.com/jquery-3.5.1.min.js"
    integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0="
    crossorigin="anonymous"></script>
      <script>
          var now = new Date();
          var start = new Date('2022-01-09');
          var timeDiff = now.getTime() - start.getTime();
          var day = Math.floor(timeDiff / (1000 * 60 * 60 * 24) + 1);
          $('#love').text(day+'일째')
          console.log(day);
  
          var christmas = new Date('2023-12-25');
          var timeDiff2 = christmas.getTime() - now.getTime();
          var day2 = Math.floor(timeDiff2 / (1000 * 60 * 60 * 24) + 1);
          console.log(day2);
          $('#christmas').text(day2+'일 남음');
  
          var ms = start.getTime() + 999 *(1000 * 60 * 60 * 24);
          var 천일 = new Date(ms);
          var 천일날짜 = 천일.getFullYear() + '.' + (천일.getMonth()+1) + '.' + 천일.getDate();
          var timeDiff3 = 천일.getTime() - now.getTime();
          var day3 = Math.floor(timeDiff3 / (1000 * 60 * 60 * 24) + 1);
          console.log(천일);
          $('#thousand-date').text(천일날짜);
          $('#thousand').text(day3+'일 남음');
  
      </script>
  ```