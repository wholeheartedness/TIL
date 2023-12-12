# 홈페이지 만들기



1. **index.html 파일을 만듭니다.**

   - ! + space bar 를 누르면 html 양식이 자동 완성 됩니다.

     ```html
     <!DOCTYPE html>
     <html lang="en">
     <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
     </head>
     <body>
       
     </body>
     </html>
     ```

     <br>

     

2. **style.css 파일을 만듭니다.**

3. **html 파일 헤더 가장 마지막에 아래 문구를 추가하여 css 파일을 링크시켜줍니다.**

   ```html
     <link rel="stylesheet" href="style.css">
   ```

   

4. **css를 쉽게 꾸미기 위하여 Bootstrap을 적용합니다.**

   - 🖥️ https://getbootstrap.com/

   - 사이트에 접속 후 All releases에 접속합니다.

     ![image-20231212091613583](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212091613583.png)

   - 원하는 버전을 선택후 CSS 소스코드를 복사합니다.

     ![image-20231212091652217](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212091652217.png)

   - HTML코드로 돌아와 CSS와 링크 시켰던 헤더의 가장 마지막 줄 위에 copy한 소스코드를 붙여넣습니다.

     ![image-20231212091753083](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212091753083.png)

   - 부트스트랩을 자바스크립트 코드에도 적용시켜야 정상적으로 동작합니다.

   - 부트스트랩 홈페이지의 CSS 하단 JS  코드를 복사합니다.

     ![image-20231212091918054](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212091918054.png)

   - html 코드로 돌아와 Body의 가장 끝 부분에 소스코드를 붙여넣습니다.

     ![image-20231212092025176](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212092025176.png)

<br>

5. **부트스트랩의 스타일 버튼 적용을 해보겠습니다.**

   - 기존 버튼 태그 스타일은 아래와 같습니다.

     ![image-20231212093410267](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212093410267.png)

   -  부트스트랩 홈페이지에서 button을 검색하면 예시와 함께 해당하는 소스코드를 가져올 수 있습니다.

     <img src="https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212093508573.png" alt="image-20231212093508573" style="zoom: 80%;" />

6.  **적당한 줄간격을 줍니다.**

   - body class = "container"로 적용하고 h1 class를 "mt-5"로 적용하면 적당한 마진값을 줄 수 있습니다.

   - 아래는 5,6번 적용 결과입니다.

     ```html
     <body class = "container">
         <h1 class = "mt-5">나는 어떤 유형의 직장인일까?</h1>
         <button type="button" class="btn btn-success">Test Start🧑‍💼</button>
     ```

     ![image-20231212093925440](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212093925440.png)

7. **가운데 정렬을 위해 `<article> 태그를 사용하여 두 코드를 묶어주고 class를 start로 할당한 후 css에서 정의합니다.**

   💀html

    ```html
    <body class="container">
        <article class="start">
            <h1 class="mt-5 text-center">나는 어떤 유형의 직장인일까?</h1>
            <button type="button" class="btn btn-success mt-5">Test Start🧑‍💼</button>
        </article>
    ```

   <br>

   🙂css

   ```css
   .start {
     display: flex;
     flex-direction: column;
   }
   ```

   <br>

   ![image-20231212095353061](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212095353061.png)

<br>

8. **버튼을 눌렀을 때 동적 수행을 하기 위하여 js 코드를 작성합니다.**

   -  body 하단에 <script>를 작성합니다

     - article class인 start를 제이쿼리를 사용( `$(.클래스명)` )하여 불러옵니다.
     - start 함수는 start 클래스를 숨기는(`.hide()`) 작업을 수행합니다.

     ```html
     <script>
         function start() {
             $(".start").hide();
         }
     </script>
     ```

     - 버튼 클릭 시 수행하므로 `onclick` 메서드를 사용하며, `=` 연산자를 사용하여 start() 함수를 할당합니다.

     ```html
     <button type="button" class="btn btn-success mt-5" onclick = 'start();'> Test Start🧑‍💼</button>
     ```

     <br>

9. **버튼을 눌렀을 때 새로운 페이지를 나타내기 위한 코드를 작성합니다.**

   - 새로운 article에 질문지 화면을 나타내는 question 클래스를 작성합니다.

     💀html

     ```html
     <article class = "question">
         <h2>문제</h2>
     
     </article>
     ```

   - css에서 이 클래스의 display를 숨겨줍니다.

     🙂css

     ```css
     .question {
       display : none;
     }
     ```

   - start() 함수에서 question 클래스를 보여주는 코드를 추가합니다.

     💀html

     ```html
     <script>
         function start() {
             $(".start").hide();
             $(".question").show();
         }
     </script>
     ```

   - 이제 버튼을 눌렀을 때 start 클래스 화면이 사라지고 question 클래스의 화면이 표출됩니다.

     ![image-20231212100410469](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212100410469.png)

     <br>

10. 문제 풀이 진도 체크를 위한 progress bar를 추가합니다.

    - 부트스트랩 홈페이지에 `progress`를 검색하여 원하는 디자인의 bar의 소스코드를 복사합니다.

      <img src="https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212100708646.png" alt="image-20231212100708646" style="zoom:80%;" />

    - question 클래스의 상단에 추가하면 화면에서도 확인할 수 있습니다.

      ![image-20231212100804212](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212100804212.png)

    

11. **질문지 화면에 버튼을 추가해보겠습니다.**

    - 부트스트랩에서 버튼 소스코드를 복사한 후 question 클래스의 하단에 2개 추가합니다.

      ![image-20231212101202177](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212101202177.png)

    - start style에서 지정했던 정렬과 flex를 똑같이 적용합니다.

    - 이 때 start와 question 클래스는 모두 article에 속하므로 .start를 사용하여 적용했던 css코드를

    - article로 바꾸어주면 됩니다.

      🙂css

      ```css
      article {
        display: flex;
        flex-direction: column;
      }
      ```

      ![image-20231212101323212](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212101323212.png)

    - 부트캠프 클래스인 `test-center` 를 사용하여 가운데 정렬을 하고 

    - `mt-5`를 사용하여 각 요소에 마진을 줍니다 

      💀html

      ```html
      <article class="question">
          <div class="progress mt-5">
              <div class="progress-bar progress-bar-striped bg-success" role="progressbar" style="width: 25%"
                  aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"></div>
          </div>
          <h2 class="text-center mt-5">문제</h2>
          <button type="button" class="btn btn-warning mt-5">Warning</button>
          <button type="button" class="btn btn-warning mt-5">Warning</button>
      </article>
      ```

      

      ![image-20231212101558662](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212101558662.png)

<br>

<br>

12. **질문지 버튼 클릭에 따른 MBTI 점수를 할당합니다.**

    - `input type "hidden" ` : 숨겨진 입력 필드를 정의하는 것으로, 페이지 콘텐츠 내에서 값을 확인할 수 없습니다.

      - 폼 제출 시 사용자가 변경해서는 안되는 데이터를 함께 보낼 때 사용됩니다.

    - 사용자가 버튼으로 응답했을 때 응답에 따른 점수를 숨기면서 전달하기 위해 해당 키워드를 사용하여 코드를 작성합니다.

      ```html
      <input type="hidden" id="EI" value="0">
      <input type="hidden" id="SN" value="0">
      <input type="hidden" id="TF" value="0">
      <input type="hidden" id="JP" value="0">
      ```

    - question 클래스에서 사용한 버튼의 아이디를 "A"와 "B"로 지정하고 버튼을 눌렀을 때 value를 할당할 수 있도록 input을 불러옵니다.

      ```html
      <input id= "type" type="hidden" value = "EI"> 
      <button id="A" type="button" class="btn btn-warning mt-5">Warning</button>
      <button id="B" type="button" class="btn btn-warning mt-5">Warning</button>
      ```

    - script에서 ID가 "A"인 버튼을 클릭했을 때 실행할 함수를 정의합니다.

      ```js
      $("#A").click(function() {
              });
      ```

      - var형 type 변수는 ID가 type인 input 값을 가져옵니다. (EI/SN/TF/JP)가 해당합니다.

      - var형 preValue 변수는 아이디가 type(EI/SN/TF/JP)의 input의 값을 가져옵니다.

      - 아이디가 type인 input의 Value를 정수로 변환하여 1을 더합니다.

        ```js
        $("#A").click(function() {
                    var type = $("#type").val();
                    var preValue = $("#"+type).val();
                    $("#"+type).val(parseInt(preValue)+1);
                });
        ```

        <br>

        <br>

13. **버튼을 눌렀을 때 점수가 올라가고 다음 문제로 넘어가는 기능을 추가해보겠습니다.**

    - 문제 내용에 해당하는 h2 태그에 ID="title"을 할당합니다.

    - 문제에 대한 정보들을 저장할 객체를 생성합니다.

      ```js
      var num = 1;
      var quiz = {
          1: {"title" : "문제 1번", "type":"EI", "A":"E", "B":"I"},
          2: {"title" : "문제 2번", "type":"EI", "A":"E", "B":"I"},
          3: {"title" : "문제 3번", "type":"EI", "A":"E", "B":"I"}
      
      }
      ```

    - 다음 문제로 넘어가는 next 함수를 작성합니다.

      - `html()` : 선택한 요소 안의 내용을 가져오거나 다른 내용으로 바꿉니다.
      - `val()` : input 태그에 정의된 value의 속성 값을 확인합니다.
      - title, A, B는 페이지에 표출할 내용이기 때문에 html을 사용하여 값을 가져오지만
      - type은 사용자에게 숨길 정보이기 때문에 value로 값만 가져옵니다.

      ```js
      function next() {
          $("#title").html(quiz[num]["title"]);
          $("#type").val(quiz[num]["type"]);
          $("#A").html(quiz[num]["A"]);
          $("#B").html(quiz[num]["B"]);
          num++;
      }
      ```

    - next 함수를 click 시 실행되는 함수의 마지막 부분과 start 함수의 마지막에 넣어줍니다.

      ```js
      function start() {
          $(".start").hide();
          $(".question").show();
          next();
      }
      ```

      ```js
      $("#A").click(function() {
          var type = $("#type").val();
          var preValue = $("#"+type).val();
          $("#"+type).val(parseInt(preValue)+1);
          next();
      });
      $("#B").click(function() {
          next();
      });
      ```

      <br>

      <br>

14. **문제의 진척에 따른 progress bar 증를 동적으로 할당해보겠습니다.**

    - 부트스트랩에서 사용한 코드를 보겠습니다.
      - style="width:" 를 사용하여 폭을 조정하는 것을 알 수 있습니다.
      - 12문제에 대한 진척도를 확인하므로 100%를 12로 나눈 후 1단계씩 증가시키겠습니다.
      - `calc` : css에서 직접 연산이 가능한 함수입니다.

    ```html
    <div class="progress mt-5">
        <div class="progress-bar progress-bar-striped bg-success" role="progressbar" style="width: calc(100/12*1%)"
            aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"></div>
    </div>
    ```

    - next 함수가 호출될 때마다 width 값을 증가시키므로 next함수에서 bar를 연산합니다.

      - `.attr` : 해당 요소의 값을 변경합니다. 

      - key 값에 'style'을, value 값에 변경할 'width' 내용을 작성해줍니다.

        💡클래스를 호출할 때 `progress-bar progress-bar-striped bg-success` 를 사용하여 호출하였더니 동작하지 않았습니다. `"progress"` 라는 큰 클래스 안에 속한 작은 단위의 클래스를 호출하면 안되는 것 같습니다.

        

    ```js
    $(".progress-bar").attr('style', 'width: calc(100/12*'+num+'%)');
    ```

    <br>

    - progress bar가 동작합니다.

    ![image-20231212114656791](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212114656791.png)

<br>

<br>



15. 마지막 결과 화면을 만들어보겠습니다.

    - article 태그를 이용하여 result 클래스를 생성합니다.

      - 이미지, 유형 이름, 설명란에 각각 img, person, explain이라는 id를 부여합니다.

        ```html
        <article class = "result">
            <img id = "img" src = "" alt="">
            <h2 id = "person">유형 이름</h2>
            <h3 id = "explain">설명</h3>
        </article>
        ```

    - 첫 페이지에서 보이지 않도록 css로 result 클래스를 숨깁니다.

      ```css
      .result {
        display : none;
      }
      ```

      

    - next 함수에 num==13이 되었을 때 questio 클래스를 숨기고(`hide()`) result  페이지를 보여줍니다 (`show()`)

      ```js
      function next() {
          if (num == 13) {
              $(".question").hide();
              $(".result").show();
          }
          $(".progress-bar").attr('style', 'width: calc(100/12*'+num+'%)');
          $("#title").html(quiz[num]["title"]);
          $("#type").val(quiz[num]["type"]);
          $("#A").html(quiz[num]["A"]);
          $("#B").html(quiz[num]["B"]);
          num++;
      }
      ```

      

    - 문제 12번이 끝난 후 해당 페이지가 보여집니다.

      ![image-20231212115810484](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212115810484.png)

      <br>

      

16.  유형 별 사진을 넣어보겠습니다.

    - 프로젝트 폴더에 사진을 저장합니다.

    - result 클래스의 img 태그에 해당 이미지의 경로를 입력합니다.

    - 사진을 동그랗게 자르기 위해 부트스트랩의 border 클래스를 사용합니다

    - 정렬을 위해 부트스트랩의 `text-center` 와 `mt-5` 클래스를 사용합니다

      <img src="https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212130204943.png" alt="image-20231212130204943" style="zoom:80%;" />

      ```html
      <article class = "result">
          <img id = "img" class = "rounded-circle mt-5"  src = "person.jpeg" alt="" >
          <h2 id = "person" class = "text-center mt-5">유형 이름</h2>
          <h3 id = "explain" class = "text-center mt-5">설명</h3>
      </article>
      ```

      

    - 사진의 크기를 조절하기 위해 CSS에서 ID img 태그를 조절합니다.

      ```css
      #img {
        width : 300px;
        height : 300px;
        margin: 0 auto;
      }
      ```

      

    - 아래와 같이 수정됐습니다.

      <img src="https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212130409791.png" alt="image-20231212130409791" style="zoom:80%;" />

      <br>

      <br>

17. **이제 MBTI를 구하는 로직을 작성합니다.**

    - 모든 문항의 검사가 끝났을 때, id EI/SN/TF/JP에 할당된 점수를 확인 후의 결과를 출력합니다.

    - next 함수에서 문제 번호가 끝났을 때 계산된 결과를 팝업창으로 나타내는 로직입니다

      - mbti라는 스트링 변수를 선언한 후 삼항 연산자를 사용하여 각 문항의 value가 2보다 작으면 INFP를 크다면 ESTJ를 출력합니다.

      - 연산이 끝났을 때 `alert` 함수를 사용하여 팝업창에 나타냅니다.

        ```js
        function next() {
            if (num == 13) {
                $(".question").hide();
                $(".result").show();
                var mbti = "";
                ($("#EI").val() < 2) ? mbti += "I" : mbti += "E";
                ($("#SN").val() < 2) ? mbti += "N" : mbti += "S";
                ($("#TF").val() < 2) ? mbti += "F" : mbti += "T";
                ($("#JP").val() < 2) ? mbti += "P" : mbti += "J";
                alert(mbti);   
            } else {
                $(".progress-bar").attr('style', 'width: calc(100/12*' + num + '%)');
                $("#title").html(quiz[num]["title"]);
                $("#type").val(quiz[num]["type"]);
                $("#A").html(quiz[num]["A"]);
                $("#B").html(quiz[num]["B"]);
                num++;
            }
        }
        ```

    - 아래와 같이 출력됩니다.

      ![image-20231212131634235](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212131634235.png)

      <br>

      <br>

18. **각 유형별 이름, 설명, 이미지를 맵합니다.**

    ```js
    var result = {
        "ISTJ" : {"person" : "ISTJ", "explain" : "ISTJ 설명", "img" : "person.jpeg"},
        "ESTJ" : {"person" : "ESTJ", "explain" : "ESTJ 설명", "img" : "person.jpeg"},
        "ISFJ" : {"person" : "ISFJ", "explain" : "ISFJ 설명", "img" : "person.jpeg"},
        "ESFJ" : {"person" : "ESFJ", "explain" : "ESFJ 설명", "img" : "person.jpeg"},
        "INTJ" : {"person" : "INTJ", "explain" : "INTJ 설명", "img" : "person.jpeg"},
        "ENTJ" : {"person" : "ENTJ", "explain" : "ENTJ 설명", "img" : "person.jpeg"},
        "INFJ" : {"person" : "INFJ", "explain" : "INFJ 설명", "img" : "person.jpeg"},
        "ENFJ" : {"person" : "ENFJ", "explain" : "ENFJ 설명", "img" : "person.jpeg"},
        "ISTP" : {"person" : "ISTP", "explain" : "ISTP 설명", "img" : "person.jpeg"},
        "ESTP" : {"person" : "ESTP", "explain" : "ESTP 설명", "img" : "person.jpeg"},
        "ISFP" : {"person" : "ISFP", "explain" : "ISFP 설명", "img" : "person.jpeg"},
        "ESFP" : {"person" : "ESFP", "explain" : "ESFP 설명", "img" : "person.jpeg"},
        "INTP" : {"person" : "INTP", "explain" : "INTP 설명", "img" : "person.jpeg"},
        "ENTP" : {"person" : "ENTP", "explain" : "ENTP 설명", "img" : "person.jpeg"},
        "INFP" : {"person" : "INFP", "explain" : "INFP 설명", "img" : "person.jpeg"},
        "ENFP" : {"person" : "ENFP", "explain" : "ENFP 설명", "img" : "person.jpeg"}
    }
    ```

    - next 함수에서 연산한 mbti 변수와 result 변수를 매칭합니다.

      ```js 
      function next() {
          if (num == 13) {
              $(".question").hide();
              $(".result").show();
              var mbti = "";
              ($("#EI").val() < 2) ? mbti += "I" : mbti += "E";
              ($("#SN").val() < 2) ? mbti += "N" : mbti += "S";
              ($("#TF").val() < 2) ? mbti += "F" : mbti += "T";
              ($("#JP").val() < 2) ? mbti += "P" : mbti += "J";
              alert(mbti);
              $("#img").attr("src", result[mbti]["img"]);   
              $("#person").html(result[mbti]["person"]);   
              $("#explain").html(result[mbti]["explain"]);     
          } else {
              $(".progress-bar").attr('style', 'width: calc(100/12*' + num + '%)');
              $("#title").html(quiz[num]["title"]);
              $("#type").val(quiz[num]["type"]);
              $("#A").html(quiz[num]["A"]);
              $("#B").html(quiz[num]["B"]);
              num++;
          }
      }
      ```

    - 아래와 같이 결과에 따라 결과 화면이 달라집니다.

      <img src="https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231212133145074.png" alt="image-20231212133145074" style="zoom:80%;" />

<br>

<br>

😸 작성한 전체 코드 입니다.

```html
<!DOCTYPE html>
<html lang="ko">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css"
    integrity="sha384-TX8t27EcRE3e/ihU7zmQxVncDAy5uIKz4rEkgIXeMed4M0jlfIDPvg6uqKI2xXr2" crossorigin="anonymous">
  <link rel="stylesheet" href="style.css">
</head>

<body class="container">
  <!-- 👇 main 화면 -->
  <article class="start">
    <h1 class="mt-5 text-center">우리 고양이는 어떤 유형일까?</h1>
    <button type="button" class="btn btn-success mt-5" onclick='start();'> 🐈 Test Start 🐈‍⬛</button>
  </article>
  <!-- 👇 질문지 화면 화면 -->
  <article class="question">
    <div class="progress mt-5">
      <div class="progress-bar progress-bar-striped bg-success" role="progressbar" style="width: calc(100/12*1%)"
        aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"></div>
    </div>
    <h2 id="title" class="text-center mt-5">문제</h2>
    <input id="type" type="hidden" value="EI">
    <button id="A" type="button" class="btn btn-outline-success mt-5"> Warning</button>
    <button id="B" type="button" class="btn btn-outline-success mt-3">Warning</button>
  </article>
  <!-- 👇 결과 화면 -->
  <article class="result">
    <img id="img" class="rounded-circle mt-5" src="person.jpeg" alt="">
    <h2 id="person" class="text-center mt-5">유형 이름</h2>
    <h3 id="explain" class="text-center mt-5">설명</h3>
  </article>
  <!-- 👇 질문지 점수 저장 -->
  <input type="hidden" id="EI" value="0">
  <input type="hidden" id="SN" value="0">
  <input type="hidden" id="TF" value="0">
  <input type="hidden" id="JP" value="0">


  <!-- 👇 부트스트랩 -->
  <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"
    integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj"
    crossorigin="anonymous"></script>
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/js/bootstrap.bundle.min.js"
    integrity="sha384-ho+j7jyWK8fNQe+A12Hb8AhRq26LrZ/JpcUGGOn+Y7RsweNrtN/tE3MoK7ZeZDyx"
    crossorigin="anonymous"></script>

  <!-- 👇 main 화면 숨기고 문제화면 나타내기-->
  <!-- 👇 버튼 클릭에 따른 점수 가져오기-->
  <script>
    var num = 1;
    var quiz = {
      1: { "title": "집사가 사람 친구를 데리고 왔을 때 나의 반응은?🐾", "type": "EI", "A": "새사람 좋아! <br> 빨리 낚싯대를 집으라냥😽", "B": "허락도 없이 친구를 데려왔어? <br> 조용히 놀고 난 건들지마라냥😼" },
      2: { "title": "집사가 길냥이를 줍줍해왔다. 이 때 나의 반응은?", "type": "EI", "A": "우쭈쭈 작은 리를 키티... 같이 살자냥😹", "B": "이 집에 나 이외의 고양이는 불편해. <br>불쌍하지만 잠깐만 있다가 나가라냥😿" },
      3: { "title": "야옹야옹. 베란다 밖 저 소리는 나를 부르는 소리가 났을 때 나의 반응은?", "type": "EI", "A": "누가 울음 소리를 내었는가.<br>궁금하니 당장 다가가보자냥😸", "B": "강조되고 반복되는 소리는 고양이를 불안하게해요. <br>호다닥 숨는다냥🙀" },
      4: { "title": "메에...메에.. 집사가 이상한 고양이 소리를 내며 나를 유인하는 것 같다", "type": "SN", "A": "집사가 이상한 소리를 배워온 듯 하다. 무시하자냥🐈", "B": "저게 뭘 의미하는 소리지? 다가가보자냥🐈‍⬛" },
      5: { "title": "메에..아니 사실은... 집사가 주절주절 하소연을 하기 시작한다.", "type": "SN", "A": "인간 말은 몰라. 그루밍이나 하겠다냥🐾", "B": "무슨 말인지는 모르겠지만.. 일단 들어보자냥😺" },
      6: { "title": "창 밖은 신기해. 나냥이는 사실 지금", "type": "SN", "A": "멍때리고 있지. 인간이 지나가고 있다냥..😺", "B": "저건 뭘까? 오모나 세상에 저기 냥이가 또 있어! 모든게 신기하다냥🐱" },
      7: { "title": "집사의 주머니에서 나온 저것은 츄르!🍬", "type": "TF", "A": "이제 슬슬 츄르가 나올 시간이었지. 얼른 대령하라냥😼", "B": "세상에! 저 기다랗고 맛있는 간식을 주다니. 집사 짱짱맨이다냥😻" },
      8: { "title": "퀡퀡 쿨럭. 집사가 큰소리로 기침을 한다. 이때 나는?", "type": "TF", "A": "집사 상태가 평소랑 다른데? 큰소리가 나니 잠시 피해있겠다냥. 몸조리 하라냥🙀", "B": "집사 상태가 평소랑 다른데? 야옹야옹 걱정된다냥 그루밍이라도 해주겠다냥 😿" },
      9: { "title": "'너가 좋아할 것 같아서 인형 사왔어' 마음에 안드는 선물을 선물하는 집사!", "type": "TF", "A": "별론데? 관심없는데에 시간낭비하지 않아. 박스나 뜯어야겠다냥.📦 ", "B": "호오. 내껀가? 킁킁 2분 정도는 가지고 놀아주겠다냥.🐀" },
      10: { "title": "평소와 달리 일찍 일어난 집사. 열심히 집청소를 한다", "type": "JP", "A": "이 시간에 뭐하는거지? 지금은 잘 시간이야! 다시 누우라냥😾", "B": "앗 집사가 일찍 일어나 뭔가 하고있어. 나도 따라다니면서 같이 놀거다냥😸" },
      11: { "title": "어느샌가 길어버린 발톱... 집사 발톱깎이를 들고 다가온다", "type": "JP", "A": "빨리 끝내줘.. 불안하지만 참아보겠다냥🤝", "B": "악! 지금은 아니야! 와다다다 도망갈거다냥🐈" },
      12: { "title": "베트남으로 여행을 떠난 집사! 사람 친구가 틈틈이 와서 나를 돌봐주고 있다.", "type": "JP", "A": "누구지? 아무도 없는 집에 모르는 사람이 오는 건 패닉이야! 집사! 빨리오라냥!", "B": "밥이랑 물은 안떨어지는군... 하지만 집사... 빨리오라냥... " }
    }
    var result = {
      "ISTJ": { "person": "신중한 선배냥", "explain": "이 고양이는 항상 일을 신중하게 계획하고 진행하는 현명한 특징을 가지고 있습니다.<br>  안정적인 모습으로 다른 고양이들 사이에서도 <br>신뢰를 쌓는 데 능숙해요. <br>그래서 주변의 다른 동물들도 이 현명한 냥이에게 자주 조언을 구하곤 합니다.", "img": "person.jpeg" },
      "ESTJ": { "person": "내동료가되라 리더냥", "explain": "리더십이 강하고 조직적인 고양이. <br> 주변의 다른 동물들을 이끄는 역할을 하며, 체계적으로 일을 처리하는 냥이에요.", "img": "person.jpeg" },
      "ISFJ": { "person": "도와주는 친구냥", "explain": "이 고양이는 무엇이든지 도울 준비가 되어 있어요.<br> 항상 다른 고양이들에게 도움의 손길을 내밀며, <br>따뜻하고 친절한 성향으로 다양한 동물들과 소통하며 친구들을 만들어 나갑니다.", "img": "person.jpeg" },
      "ESFJ": { "person": "인간좋아 다정냥", "explain": "따뜻하고 친절한 성격의 고양이. <br>다른 동물들과의 관계를 중요시하며, 친구들과 어울리는 것을 즐기는 냥이에요.", "img": "person.jpeg" },
      "INTJ": { "person": "전략적인 수련냥", "explain": "문제를 해결하는 데에 창의적이고 전략적인 능력을 가진 냥이입니다.<br> 항상 새로운 아이디어와 혁신을 추구하면서<br> 주위를 지배하는 모습을 보여, 다른 동물들에게도 많은 영감을 주곤 합니다.", "img": "person.jpeg" },
      "ENTJ": { "person": "꿈이커요 도전냥", "explain": "리더십이 강하고 조직적인 냥이. <br>주변의 다른 동물들을 이끄는 역할을 하며, 일상 생활도 체계적으로 하는 냥이입니다.", "img": "person.jpeg" },
      "INFJ": { "person": "심오한 고민냥", "explain": "이 고양이는 깊이 생각하고 감정을 깊게 체험하는 특징이 있어요.<br> 다른 고양이들과의 상호작용에서 심미적이면서도 고요한 면을 보이며, 때로는 주변 동물들에게 조언을 해 주는 마음씨 좋은 냥이에요.", "img": "person.jpeg" },
      "ENFJ": { "person": "포용하는 인자냥", "explain": "따뜻하고 친절한 성격의 고양이.<br> 다른 동물들과의 관계를 중요시하며,<br> 친구들과 어울리는 것을 즐기는 냥이에요.", "img": "person.jpeg" },
      "ISTP": { "person": "모험을 즐기는 엄친냥", "explain": "이 고양이는 자유로운 영혼을 가졌습니다. <br>모험을 좋아하며 새로운 경험을 즐기는 특징이 있어요.<br> 호기심이 많아 어디든지 뛰어들며 주변을 적극적으로 탐험하는 냥이에요.", "img": "person.jpeg" },
      "ESTP": { "person": "에너제틱 터프냥", "explain": "활기차고 적극적인 고양이. <br>에너지가 넘치며 행동을 즐기고, <br>모험을 추구하면서 자신의 열정을 주위에 전파하는 역할을 합니다.", "img": "person.jpeg" },
      "ISFP": { "person": "게으른 예술가냥", "explain": "미적 감각이 뛰어나며 예술적인 표현을 즐기는 냥이입니다. <br>다양한 예술 활동을 통해 감정을 표현하며, <br>아름다운 행동과 미적 감각으로 주변을 화려하게 만들어 나가요.", "img": "person.jpeg" },
      "ESFP": { "person": "둥글둥글 사교냥", "explain": "사교성이 뛰어나고 활기찬 냥이.<br> 주변 동물들과 소통하며 활발하게 즐기는 사교적인 성격을 가지고 있어요.", "img": "person.jpeg" },
      "INTP": { "person": "지적인 물음표냥", "explain": "끊임없이 물음표를 던지며 지적인 호기심을 채우는 냥이입니다. <br>문제 해결에 대한 지적인 탐구와 호기심이 늘 가득하며, <br>주변 동물들과의 흥미로운 대화에서 항상 새로운 관점을 제시하는 냥이에요.", "img": "person.jpeg" },
      "ENTP": { "person": "창의적인 자유파냥", "explain": "열정 넘치고 자유로운 영혼을 지닌 고양이.<br> 새로운 경험을 추구하며 <br>동료들에게 긍정적인 영향을 주는 역할을 하는 냥이에요.", "img": "person.jpeg" },
      "INFP": { "person": "꿈꾸는 낭만냥", "explain": "이 고양이는 상상력이 풍부하고 깊은 감정을 지니고 있어요.<br> 항상 꿈을 키우며 새로운 가능성을 찾아다니며 <br>주변 동물들에게 긍정적인 에너지를 전파하는 냥이입니다.", "img": "person.jpeg" },
      "ENFP": { "person": "열정만땅 말괄량이냥", "explain": "노는게 제일 좋아! 당신의 고양이는 낚싯대와 집사를 가장 좋아할 것 같아요", "img": "person.jpeg" }
    }
    function start() {
      $(".start").hide();
      $(".question").show();
      next();
    }

    $("#A").click(function () {
      var type = $("#type").val();
      var preValue = $("#" + type).val();
      $("#" + type).val(parseInt(preValue) + 1);
      next();
    });
    $("#B").click(function () {
      next();
    });
    function next() {
      if (num == 13) {
        $(".question").hide();
        $(".result").show();
        var mbti = "";
        ($("#EI").val() < 2) ? mbti += "I" : mbti += "E";
        ($("#SN").val() < 2) ? mbti += "N" : mbti += "S";
        ($("#TF").val() < 2) ? mbti += "F" : mbti += "T";
        ($("#JP").val() < 2) ? mbti += "P" : mbti += "J";
        alert(mbti);
        $("#img").attr("src", result[mbti]["img"]);
        $("#person").html(result[mbti]["person"]);
        $("#explain").html(result[mbti]["explain"]);
      } else {
        $(".progress-bar").attr('style', 'width: calc(100/12*' + num + '%)');
        $("#title").html(quiz[num]["title"]);
        $("#type").val(quiz[num]["type"]);
        $("#A").html(quiz[num]["A"]);
        $("#B").html(quiz[num]["B"]);
        num++;
      }
    }
  </script>
</body>

</html>
```



