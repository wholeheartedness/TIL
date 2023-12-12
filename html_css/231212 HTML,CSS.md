## 1. HTML

- 문서의 골격을 만드는 작업

  - 잘 쓰이는 태그를 중심으로 사용

    ![image-20231211153418808](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231211153418808.png)

<br>



- `!DOCTYPE html` : HTML 문서임을 가르킴 (필수)
- `<html>` : HTML 문서임을 가르킴 (필수)

<br>



### Head 태그 : 부가정보 (여행가방 수화물 태그)

- `<meta charset = "UTF-8">` : 한글 출력
- `<title>` : 주소줄 라인 이름 지정
- `<link rel = "stylesheet" href = "파일명.css">` : css파일 연결

<br>



### Body 태그 : 모든 콘텐츠 (여행가방 안 물건)

- `<h1>`
- `<p>` 
- `<footer>`

<br>

<br>

<br>



## 2. CSS

- 문서에 살을 입히자

  

![image-20231211170225951](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231211170225951.png)

- `P(클래스명)` : html에 작성된 태그명

- `.P(클래스명)` : class 지정 시 바로 연결  

  ```html
  <!DOCTYPE html>
  <html>
  <head>
    <meta charset = "UTF-8"> 
    <title> 이서주의 이력서 </title>
    <link rel = "stylesheet" href="css.css">
  </head>
  <body>
    <p class = "big-font"> 내이름은 이효리</p>
    <p> 거꾸로 말해도 이효리 </p>
    <p class = "small-font"> 이효리 짱 </p>
    </body>
  </html>
  ```

  ```css
  p {
    font-size : 20px;
  }
  
  .big-font {
    font-size : 40px;
  }
  
  .small-font {
    font-size : 10px;
  }
  ```

  <br>

  

- `text-align` : 글자 정렬

- `color` : 글자색 지정

- `footer` 

- `font-size` : 폰트 크기 지정

<br>



- `border ` : 박스 지정

  ```css
  .box1 {
    background-color : skyblue;
    width: 60px;
    height: 60px;
    border : 20px solid black;
  }
  
  .box2 {
    background-color : violet;
    width: 100px;
    height: 100px;
  }
  ```

  ![image-20231211173733828](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231211173733828.png)

- `box-shadow`: 박스 그림자 설정

  ```box-shadow: none | x-position y-position blur spread color | inset | initial | inherit```

  ```box-shadow: 0 1px 20px 0 rgba(0,0,0,0.1);```

  <br>

  

- `none` : 그림자 효과를 없앤다.

- `x-position` : 가로 위치이다. 양수면 오른쪽에, 음수면 왼쪽에 그림자가 만들어진다. (필수)

- `y-position` : 세로 위치이다. 양수면 아래쪽에, 음수면 위쪽에 그림자가 만들어진다. (필수)

- `blur` : 그림자를 흐릿하게 만든다. 값이 클 수록 더욱 흐려진다.

- `spread` : 양수면 그림자를 확장하고, 음수면 축소한다.

- `color` : 그림자 색을 정한다.

- `inset` : 그림자를 요소의 안쪽에 만든다.

- `initial` : 기본값으로 설정한다.

- `inherit` : 부모 요소의 값을 상속받는다.

  <br>

  

- `@import url('url주소');` : 폰트 추가 
- `font-family` : 폰트 선택
- `*{ }` : 문서 전체에 적용

<br>



- `<section>, <article>` : div 중첩이 많을 때 읽기 쉽게 만들어줌

<br>



- `float` : 둥둥 떠다니며 정렬

- `overflow: hidden;` : flaot를 잘 정렬

  ```html
  <!DOCTYPE html>
  <html>
  <head>
      <meta charset="UTF-8">
      <title> 이서주의 이력서 </title>
      <link rel="stylesheet" href="css.css">
  </head>
  <body>
  <div class="mainbox">
      <h1> 이 서 주 </h1>
      <p> HTML/CSS 개발자 </p>
      <section>
          <h2>About Me</h2>
          <p class="about-me-text">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et  dolore magna aliqua.Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod.
  
          </p>
          <section>
              <h2> EXPERIENCE </h2>
              <div class="float-wrap">
                  <p class="title-text"> Awesome Programming Company </p>
                  <p class="year-text"> 2020-now </p>
              </div>
              <p class="desc-text"> Front-End Web Developer</p>
              <p class="desc-subtext"> HTML/CSS, JS, JAVA </p>
  
              <div class="float-wrap">
                  <p class="title-text"> Awesome Programming Company </p>
                  <p class="year-text"> 2018-2022 </p>
              </div>
              <p class="desc-text"> Front-End Web Developer</p>
              <p class="desc-subtext"> HTML/CSS, JS, JAVA </p>
  
              <div class="float-wrap">
                  <p class="title-text"> Awesome Programming Company </p>
                  <p class="year-text"> 2018-2022 </p>
              </div>
  
              <p class="desc-text"> Front-End Web Developer</p>
              <p class="desc-subtext"> HTML/CSS, JS, JAVA </p>
  
          </section>
      </section>
      <div class="sns-wrap">
          <a href = "http://instagram.com"> <img class="sns-img"
               src=이미지 url></a>
                 <a href = "http://instagram.com"> <img class="sns-img"
               src=이미지 url></a>
                       <a href = "http://instagram.com"> <img class="sns-img"
               src=이미지 url></a>
      </div>
  </div>
  <footer>
      <p> copyright </p>
  </footer>
  </body>
  </html>
  ```

  ```css
  @import url('https://fonts.googleapis.com/css?family=Montserrat:100,200,300,400,500,600,700,800&display=swap');
  *{
    font-family : 'Montserrat';
  }
  
  body,h1,h2 {
    margin: 5px;
    padding: 5px;
  }
  
  body {
    min-width: fit-content;
  }
  
  h1 {
    font-size : 30px;
    font-width: bold;
    font-style : italic;
  }
  
  h2 {
    font-size: 20px;
    font-weight: bold;
    color: #282828;
    border-bottom: 1px solid #ebebeb;
    text-align: left;
    margin-bottom: 10px;
    margin-left: 10px;
    margin-right: 10px;
  }
  
  footer {
    text-align: center;
    background-color: #8C8CFF;
    color: #5A5AFF;
    font-size: 12px;
  }
  
  .name-text {
    font-size: 17px;
    color : #7c7c7c;
    font-weight: bold;
  }
  
  .mainbox {
    border: 1px solid #8C8CFF;
    width : 610px;
    margin-left : auto;
    margin-right : auto;
    text-align : right;
    padding: 30px;
    margin: 10px;
    box-shadow: 0 50px 20px 0 rgba(0,0,0,0.2);
  }
  
  .box1 {
    background-color : skyblue;
    width: 60px;
    height: 60px;
    border : 5px solid black;
    padding: 20px;
  }
  
  .box2 {
    background-color : violet;
    width: 100px;
    height: 100px;
    border: 5px solid purple;
  }
  
  section {
    margin-bottom : 24px;
  }
  
  .name-text {
    font-size : 16px;
    color : #7c7c7c;
    font-weight : bold;
  }
  
  .about-me-text {
    font-size: 10px;
    line-height : 16px;
    text-align: left;
    margin: 10px;
  }
  
  .title-text {
    font-size : 11px;
    font-weight : bold;
    color: #282828;
    float: left;
  }
  
  .year-text {
    font-size : 11px;
    font-weight : bold;
    color: #282828;
    float: right;
  }
  
  .float-wrap {
    overflow: hidden;
  }
  
  .desc-text {
    font-size : 11px;
    text-align: left;
  }
  
  .desc-subtext {
    font-size: 11px;
    color: #282828;
    padding-left: 16px;
    text-align: left;
  }
  
  .sns-img {
    width: 12px;
    height: 12px;
  }
  
  .sns-wrap {
    text-align: left;
  }
  ```

  