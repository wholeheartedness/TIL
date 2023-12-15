# Bootstrap

- 오픈소스 프론트엔드 프레임워크인 `부트스트랩(Bootstrap)` 입니다.
- 미리 만들어진 CSS와 Javascript를 활용합니다
  - CSS 속성을 쉽게 적용할 수 있습니다.

<br>

<br>

<br>



---



## 1. 부트스트랩 적용하기

1️⃣ 부트스트랩 문서에 들어갑니다

​	🖥️https://getbootstrap.com/docs/5.3/getting-started/introduction/

<br>

2️⃣ 1. Quick Start - 2. Include Bootstrap's CSS and JS. 의 코드를 복사하여 사용할 html 파일에 붙여 넣습니다.

![image-20231215133511103](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215133511103.png)

- 💡 붙여놓은 소스는 CDN Link로 가장 최신버전의 Bootstrap 버전을 적용 시킬 수 있는 코드입니다.

![image-20231215133607378](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215133607378.png)

<br>

<br>

<br>

---



## 2. Bootstrap 사용하기

- 기존에는  html에 contents를 작성하고 CSS에서 생성자를 이용하여 일일이 스타일을 적용하여 줬지만
- 부트스트랩을 사용하면 html에서 간편하게 스타일을 적용시킬 수 있습니다.



### 1️⃣ TEXT

🖥️https://getbootstrap.com/docs/5.3/utilities/text/#text-alignment

<br>



- #### 정렬

  ```html
      <p class = "text-start"> text-start class 적용 </p>
      <p class = "text-center"> text-center class 적용 </p>
      <p class = "text-end"> text-end class 적용 </p>
  ```

  ![image-20231215135210524](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215135210524.png)

<br>

- #### 박스안에 글자 넣기

  ```html
  <div class="badge bg-primary text-wrap" style="width: 10rem;">
    박스 안의 글자
  </div>
  ```

  

![image-20231215135118880](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215135118880.png)

​	📌 rem = font-size 속성값에 비례하여 결정되는 상대 단위 (최상위 요소 font-size)

- ex) font - size : 16px
  - 1 rem = 16px / 2 rem = 32px ...





<br>

- #### 굵기 지정

  ```html
  <p class="fw-bold">Bold text.</p>
  <p class="fw-bolder">Bolder weight text (relative to the parent element).</p>
  <p class="fw-semibold">Semibold weight text.</p>
  <p class="fw-medium">Medium weight text.</p>
  <p class="fw-normal">Normal weight text.</p>
  <p class="fw-light">Light weight text.</p>
  <p class="fw-lighter">Lighter weight text (relative to the parent element).</p>
  <p class="fst-italic">Italic text.</p>
  <p class="fst-normal">Text with normal font style</p>
  ```

  ![image-20231215135302988](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215135302988.png)

<br>

- #### 글자 간격

  ```html
  <p class="lh-1">This is a long paragraph written to show how the line-height of an element is affected by our utilities. Classes are applied to the element itself or sometimes the parent element. These classes can be customized as needed with our utility API.</p>
  <p class="lh-sm">This is a long paragraph written to show how the line-height of an element is affected by our utilities. Classes are applied to the element itself or sometimes the parent element. These classes can be customized as needed with our utility API.</p>
  <p class="lh-base">This is a long paragraph written to show how the line-height of an element is affected by our utilities. Classes are applied to the element itself or sometimes the parent element. These classes can be customized as needed with our utility API.</p>
  <p class="lh-lg">This is a long paragraph written to show how the line-height of an element is affected by our utilities. Classes are applied to the element itself or sometimes the parent element. These classes can be customized as needed with our utility API.</p>
  ```

  ![image-20231215135344007](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215135344007.png)

<br>

- #### 밑줄과 취소선

  ```html
  <p class="text-decoration-underline"> 밑줄 긋기 </p>
  <p class="text-decoration-line-through"> 취소선 그리기 </p>
  ```

  ![image-20231215135456063](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215135456063.png)

  <br>

  <br>

---



### 2️⃣ Color

🖥️https://getbootstrap.com/docs/5.3/customize/color/#using-the-new-colors

<br>

- #### 글자 색

  ```html
  <p class="text-primary"> text-primary </p>
  <p class="text-secondary"> text-secondary </p>
  <p class="text-success"> text-primary </p>
  <p class="text-danger"> text-primary </p>
  <p class="text-warning"> text-primary </p>
  <p class="text-white bg-black"> text-primary </p>
  ```

  ![image-20231215140424041](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215140424041.png)

<br>

- #### 바탕색

  ```html
  <p class="bg-primary">bg-primary</p>
  <p class="bg-secondary">bg-secondary</p>
  <p class="bg-success">bg-success</p>
  <p class="bg-danger">bg-danger</p>
  <p class="bg-warning">bg-warning</p>
  ```

  ![image-20231215140652990](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215140652990.png)

<br>

<br>

---



### 3️⃣ box-model

- #### 박스 크기 조절

  - 부모 요소의 width, height 50%로 박스를 만들어 보겠습니다.

  ```html
  <div style="width: 500px; height: 500px;" class="bg-secondary">
    <div class="w-50 h-50 bg-primary"> test </div>
  </div>
  ```

  ![image-20231215141007595](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215141007595.png)

  <br>

  ```html
  <div style="width: 500px; height: 500px;" class="bg-light">
    <div class="w-50 h-50 bg-primary">
      <div class="w-50 h-50 bg-primary-subtle">
        <div class="w-50 h-50 bg-secondary"></div>
      </div>
    </div>
  </div>
  ```

  ![image-20231215141326708](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215141326708.png)

  <br>

  <br>

---



### 4️⃣ Margin, Padding

🖥️https://getbootstrap.com/docs/5.3/utilities/spacing/#margin-and-padding

<br>



- Margin - m

- Padding - p

  <br>

  - margin or padding 포지션

    - t : top

    - b : bottom

    - s : start :: left (LTR), right (RTL)

    - e : end :: right (LTR), right (RTL)

      <br>

  - margin or padding 사이즈

    - 0~5 
    - auto (margin만 적용)

  ```html
  <div style="width: 500px; height: 500px;" class="bg-light p-5">
    <div class="w-50 h-50 bg-primary ps-4">
      <div class="w-50 h-50 bg-primary-subtle pt-3">
        <div class="w-50 h-50 bg-secondary mt-5"></div>
      </div>
    </div>
  </div>
  ```

  ![image-20231215141904093](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215141904093.png)

  

<br>

<br>

---



### 5️⃣ Flex

🖥️https://getbootstrap.com/docs/5.3/utilities/flex/#enable-flex-behaviors

<br>



- #### flex container와 item 생성

  ```html
  <div class="w-100 d-flex bg-primary-subtle p-3"> container
    <div style = "width:100px; height: 100px;" 
    class="text-bg-primary">0</div>
    <div style = "width:100px; height: 100px;" 
    class="text-bg-primary">1</div>
    <div style = "width:100px; height: 100px;" 
    class="text-bg-primary">2</div>
    <div style = "width:100px; height: 100px;" 
    class="text-bg-primary">3</div>
  </div>
  ```

  ![image-20231215142749236](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215142749236.png)

<br>

- #### flex-column

  ```html
  <div class="w-100 d-flex bg-primary-subtle p-3 flex-column"> container
    <div style = "width:100px; height: 100px;" 
    class="text-bg-primary">0</div>
    <div style = "width:100px; height: 100px;" 
    class="text-bg-primary">1</div>
    <div style = "width:100px; height: 100px;" 
    class="text-bg-primary">2</div>
    <div style = "width:100px; height: 100px;" 
    class="text-bg-primary">3</div>
  </div>
  ```

  ![image-20231215143019404](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215143019404.png)

<br>

<br>

---



### 6️⃣ Button

- #### 색상별 버튼 생성

  ```html
  <button type="button" class="btn btn-primary">Primary</button>
  <button type="button" class="btn btn-secondary">Secondary</button>
  <button type="button" class="btn btn-success">Success</button>
  <button type="button" class="btn btn-danger">Danger</button>
  <button type="button" class="btn btn-warning">Warning</button>
  <button type="button" class="btn btn-info">Info</button>
  <button type="button" class="btn btn-light">Light</button>
  <button type="button" class="btn btn-dark">Dark</button>
  
  <button type="button" class="btn btn-link">Link</button>
  ```

  ![image-20231215143453861](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215143453861.png)

<br>

- #### 아웃라인 버튼

  ```html
  <button type="button" class="btn btn-outline-primary">Primary</button>
  <button type="button" class="btn btn-outline-secondary">Secondary</button>
  <button type="button" class="btn btn-outline-success">Success</button>
  <button type="button" class="btn btn-outline-danger">Danger</button>
  <button type="button" class="btn btn-outline-warning">Warning</button>
  <button type="button" class="btn btn-outline-info">Info</button>
  <button type="button" class="btn btn-outline-light">Light</button>
  <button type="button" class="btn btn-outline-dark">Dark</button>
  ```

  ![image-20231215143531552](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215143531552.png)

<br>

- #### 버튼 사이즈 (Large / Small)

  ```html
  <button type="button" class="btn btn-primary btn-lg">Large button</button>
  <button type="button" class="btn btn-secondary btn-lg">Large button</button>
  <button type="button" class="btn btn-primary btn-sm">Small button</button>
  <button type="button" class="btn btn-secondary btn-sm">Small button</button>
  ```

  ![image-20231215143642862](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215143642862.png)

  ![image-20231215143651201](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215143651201.png)

<br>

<br>

<br>

---



## 3. 부트스트랩 Grid System (부제: 반응형 웹)

- `반응형 웹` : 디스플레이의 사이즈에 따라서 출력이 다르게 변하는 웹페이지를 의미합니다.

  <br>

- container-fluid : 화면 크기에 꽉 채워 동적으로 할당

- container : view port 크기에 따라 동적으로 할당

  ![image-20231215144611006](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215144611006.png)

![image-20231215144619945](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215144619945.png)

<br>

- row 클래스를 만들고 column 0을 넣으면 동일한 간격으로 배치할 수 있습니다.

![image-20231215154310068](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215154310068.png)

<br>

- column에 크기를 지정할 수 있습니다.

  ```html
  <div class="container-fluid fs-2 bg-primary-subtle">
  <div class="row">
    <div class="col border border-black border-3"> col 0 </div>
    <div class="col border border-black border-3"> col 0 </div>
    <div class="col border border-black border-3"> col 0 </div>
  </div>
  </div>
  <div class="container fs-2 bg-primary">
  <div class="row">
    <div class="col-4 border border-black border-3"> col 4 </div>
    <div class="col-6 border border-black border-3"> col 6 </div>
    <div class="col border border-black border-3"> col 0 </div>
  </div>
  </div>
  ```

  ![image-20231215150611243](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215150611243.png)

  <br>

  

  - row가 한 줄에 col 12라고 생각하면 됩니다.

  ![image-20231215150832037](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215150832037.png)

<br>

<br>

---



### 🔶 Gutters

- 열 사이 패딩으로, 콘텐츠간 간격을 맞추고 정렬할 수 있습니다.

  - `gy-*(size)` , `gx-*(size)` 로 조절합니다.

  ```html
  <div class="container text-center">
  <div class="row gy-3 gx-3">
    <div class="col-6">
      <div class="bg-success py-2">간격 벌리기</div>
    </div>
    <div class="col-6">
      <div class="bg-success py-2">간격 벌리기</div>
    </div>
    <div class="col-6">
      <div class="bg-success py-2">간격 벌리기</div>
    </div>
    <div class="col-6">
      <div class="bg-success py-2">간격 벌리기</div>
    </div>
  </div>
  </div>
  <br>
  ```

  ![image-20231215151459064](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215151459064.png)

<br>

<br>

---



#### 🔶 Breakpoints

- 창크기에 따라 보여지는 아이템의 수를 다르게 표현할 수 있습니다.

- `breakpoints` 를 사용합니다.

  ![image-20231215153436110](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215153436110.png)

- 사용 예 입니다.

  ```html
  <div class = "container-fluid">
  <div class="row gx-0">
    <div class="col-6 col-sm-4 col-md-3 col-lg-1"> 
      <div class="text-bg-primary p-1"> col-6-4 </div>
    </div>
    <div class="col-6 col-sm-4 col-md-3 col-lg-1"> 
      <div class="text-bg-warning p-1"> col-6-4 </div>
    </div>
    <div class="col-6 col-sm-4 col-md-3 col-lg-1"> 
      <div class="text-bg-warning p-1"> col-6-4 </div>
    </div>
    <div class="col-6 col-sm-4 col-md-3 col-lg-1"> 
      <div class="text-bg-primary p-1"> col-6-4 </div>
    </div>
    <div class="col-6 col-sm-4 col-md-3 col-lg-1"> 
      <div class="text-bg-primary p-1"> col-6-4 </div>
    </div>
    <div class="col-6 col-sm-4 col-md-3 col-lg-1"> 
      <div class="text-bg-primary p-1"> col-6-4 </div>
    </div>
    <div class="col-6 col-sm-4 col-md-3 col-lg-1"> 
      <div class="text-bg-primary p-1"> col-6-4 </div>
    </div>
    <div class="col-6 col-sm-4 col-md-3 col-lg-1"> 
      <div class="text-bg-primary p-1"> col-6-4 </div>
    </div>
    <div class="col-6 col-sm-4 col-md-3 col-lg-1"> 
      <div class="text-bg-primary p-1"> col-6-4 </div>
    </div>
    <div class="col-6 col-sm-4 col-md-3 col-lg-1"> 
      <div class="text-bg-primary p-1"> col-6-4 </div>
    </div>
    <div class="col-6 col-sm-4 col-md-3 col-lg-1"> 
      <div class="text-bg-primary p-1"> col-6-4 </div>
    </div>
    <div class="col-6 col-sm-4 col-md-3 col-lg-1"> 
      <div class="text-bg-primary p-1"> col-6-4 </div>
    </div>
  </div>
  </div>
  ```

- `x` = 12/`size` 를 이용하면 몇개의 컨텐츠가 보일 지(`x`) 계산할 수 있습니다.

  - col-lg-1 : 화면이 lg 사이즈 일 때 column을 12개를 보여줍니다

    ![image-20231215153853630](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215153853630.png)

  - col-md-3 : 화면이 md 사이즈 일 때 column을 4개 보여줍니다.

  - ![image-20231215153833876](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215153833876.png)

  - col-sm-4 : 화면이 sm 사이즈 일 때 column을 3개 보여줍니다.

    ![image-20231215153825707](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215153825707.png)

  - (col-6 : column이 12기준 크기라서 가장 작을때는 2개를 보여줍니다) 

    ![image-20231215153817281](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231215153817281.png)