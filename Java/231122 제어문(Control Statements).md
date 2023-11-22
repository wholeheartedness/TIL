# 제어문 (Control Statements)

<br/>

## 1. 조건문 - if

<br/>

### 1.1 if문

- 어떤 조건(boolean)에 대해 코드를 실행할지 말지 결정하는 제어문

- `if <boolean 조건문>` 으로 시작합니다.

  <br/>

- if를 여러개 나열 할 수 있습니다.

  ```java
  int multiple = scanner.nextInt();
  // multiple이 2의 배수면, 2의 배수 출력
  if (multiple % 2 == 0) {
      System.out.println("2의 배수");
  }
  // multiple이 5의 배수면, 5의 배수 출력
  if (multiple % 5 == 0){
      System.out.println("5의 배수");
  }
  // multiple이 10의 배수면, 10의 배수 출력
  if (multiple % 10 == 0){
      System.out.println("10의 배수");
  ```

  > 아래와 같이 출력됩니다.
  >
  > ⬇️ 1 입력
  > ![image-20231122102027452](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231122102027452.png)
  >
  > ⬇️10 입력 
  > ![image-20231122113628190](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231122113628190.png)
  >
  > ⬇️12  입력
  > ![image-20231122101954053](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231122101954053.png)

<br/>

  - 다중 if문도 가능합니다.

    ```java
    int year = scanner.nextInt();
    if (year % 4 ==0) {
        if (year % 100 != 0) {
            System.out.println("평년이다");
        }
        if (year % 400 != 0) {
            System.out.println("윤년이다");
        }
    }
    ```

<br/>

<br/>

### 1.2. else - if문

<br/>

- 여러 조건이 필요할 때는 else-if문을 사용합니다.
- if의 조건을 제외한 가정은 else문으로 작성합니다.

```java
int number = 5;
if (number % 2 == 0) {
    System.out.println("짝수");
} else {
    System.out.println("홀수");
}
```

> "홀수"가 출력됩니다.

<br/>

- 공기질 모니터링 시스템으로 테스트 해보겠습니다.

```java
// 공기질 모니터링 시스템
// 0 ~ 30: 좋음
// 31 ~ 80: 보통
// 80 ~ 150: 나쁨
// 151 ~ : 매우 나쁨
int dust = 155;
int dust = 15;
if (dust <= 30) {
    System.out.println("좋음");
} else if (30 < dust && dust <= 80) {
    System.out.println("보통");
} else if (80 < dust && dust <= 150) {
    System.out.println("나쁨");
} else {
    System.out.println("매우 나쁨");
}
```

> 아래와 같이 출력됩니다.
>
> ![image-20231122111838489](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231122111838489.png)

<br/>

- 아래의 문제를 풀어보겠습니다.

  >  어떤 학생의 시험점수가 정수로 주어진다.
  > 점수가 90점 이상이면 "수",
  > 점수가 80점 이상 90점 미만이면 "우",
  > 점수가 80점 미만이면 "미"
  > 를 출력하여라.

  ```java
  int scores = scanner.nextInt();
  if (scores >= 0 && scores < 101) {
      if (scores >= 90) {
          System.out.println("수");
      } else if (scores >= 80 && scores < 90) {
          System.out.println("우");
      } else {
          System.out.println("미");
      }
  } else {
      System.out.println("잘못된 입력입니다");
  }
  ```

  > score의 정상범위를 미리 설정해두고 (0~100)
  >
  > 그 안에서  조건을 실행하게 했습니다.
  >
  > (else로 `scores > 100 && socres < 0` 라고 조건을 잡아줄 수 있지만,  **애초에 조건 자체가 해당되지 안되면 다른 if-else 구문을 실행할 필요가 없기 때문**입니다.)
  >
  > 
  >
  > 101을 입력 시 아래와 같이 출력되고
  >
  > ![image-20231122113127691](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231122113127691.png)
  >
  > 100을 입력 시 아래와 같이 출력됩니다.
  >
  > ![image-20231122113137803](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231122113137803.png)

<br/>

- 단, 하나의 조건을 찾는다면 아래와 같이 사용합니다.

  ``` java
  int zero = 0;
  if (zero == 0) {
      System.out.println("is zero");
  }
  else if (10 % zero == 0) {
      System.out.println("is factor");
  }
  else {
      System.out.println("not factor");
  }
  ```

  > 하나의 조건만 맞으면 다른 조건은 확인 자체를 하지 않습니다.

<br/>

<br/>

### 1.3. switch - case문

- `switch` : 만약 확인하는 조건이 **어떤 데이터** 인지 중요할 때!

  - 어떤 특정 변수의 값에 따라 실행될 코드를 분리하는 제어문

  ```java
  switch (<확인할 값>) {
  	case <비교할 값>:
          <실행할 코드>
  		break;
      default:
          <실행할 코드>
          break;
  }
  ```

- `case` : 확인할 값과 비교하여 적합할 때 실행할 코드입니다.

  <br/>

- `break` : break에 걸리면 "할일 끝!"으로 switch-case문을 탈출합니다.

  - 만약 break가 없으면 조건을 만족해도 아래 case 문으로 내려갈 수 있습니다.

    <br/>

- `default` : 모든 case에 맞는 값이 아닐 때 실행 합니다.

  - 생략 가능합니다 

<br/>

- 아래의 문제를 풀어보겠습니다

  > w, a, s, d의 입력을 받아 각각의 방향을 나타내는 코드를 작성하라.

  ```java
  String input = scanner.next();
  //확인하고 싶은 값
  switch (input) {
      case "w": // input == "w"
          System.out.println("up");
          break;
      case "a": // input == "a"
      System.out.println("left");
          break;
      case "s": // input == "s"
      System.out.println("down");
          break;
      case "d": // input == "d"
      System.out.println("right");
          break;
      // 기본동작, 필수가 아님
      default:
          System.out.println("invalid");
          break;
  }
  ```

  > w를 입력하면 아래와 같이 출력되고
  >
  > ![image-20231122114901773](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231122114901773.png)
  >
  > A를 입력하면 아래와 같이 출력됩니다.
  >
  > ![image-20231122114805535](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231122114805535.png)

  <br/>

- 위와 같은 내용을 아래와 같이도 작성 가능합니다.

  ```java
  switch (input) {
      case "w" ->
              System.out.println("up");
      case "a" ->
              System.out.println("left");
      case "s" ->
              System.out.println("down");
      case "d" ->
              System.out.println("right");
  }
  ```

<br/>

<br/>

<br/>

## 2. 반복문

<br/>

- 특정 조건(boolean)이 true일 동안 계속해서 실행하는 반복문입니다.

- `for` : 반복 횟수가 중요 한 경우

- `while` : for 외의 경우

  <br/>

  💡주의 사항

  - for문 밖에서 선언한 변수는 for문 안에서 쓸 수 있지만
  - for문 안에서 선언한 변수는 for문 밖에서 쓸 수 없습니다.

### 2.1. while문

- 조건을 만족할 때 까지 while 문 안의 코드를 실행합니다.

  <br/>

- 카페에 적립된 포인트를 소진하는 내용으로 테스트를 해보겠습니다.

  ```java
  int loan = 50000;
  int months = 0;
  while ( loan > 0 ) {
      loan -= 5000;
      months++;
      System.out.println(String.format("남은 포인트 : %d", loan));
  }
  System.out.println(String.format("포인트 소진 완료! 총 걸린 개월 수 : %d", months));
  ```

  > 아래와 같이 출력 됩니다.
  >
  > ![image-20231122132338422](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231122132338422.png)

  <br/>

  

- 배열의 총 합과 평균을 구하는 내용으로 테스트를 해보겠습니다.

  ```java
  int[] numberss = {2, 3, 5, 6, 19, 23};
  int ii = 0;
  // 총합 및 평균 구하기
  int summ = 0;
  while ( ii < numberss.length ) {
      summ += numberss[ii];
      ii++;
  }
  System.out.println("총합 :" + summ);
  System.out.println("평균 :" + sum / numberss.length);
  ```

  > 배열의 메소드인  length를 사용하여 배열의 길이를 구할 수 있습니다.  int ii는 몇번째 배열인지 가르키는 인수입니다.
  >
  > 아래와 같이 출력 됩니다.
  >
  > ![image-20231122133417865](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231122133417865.png)

<br/>

<br/>

### 2.2. for문

- 세부분으로 나누어서 반복할 조건을 설정하는 반복해서 실행합니다.

- `for (초기화 ; 조건식 ; 증감식) { }`

  - `초기화` : 반복 시작 전 실행 코드

  - `조건식` : 반복을 유지할 조건

  - `증감식` : 반복 한번 마다 실행할 코드

    <br/>

- 배열의 총합과 배열 내 최댓값, 평균값을 구하는 내용으로 테스트를 해보겠습니다.

  ```java
  int sum = 0;
  int max = -100;
  for (int i = 0; i < numbers.length; i++) {
      sum += numbers[i];
      if (numbers[i] > max) {
          max = numbers[i];
      }
  }
  System.out.println("총합 :" + sum);
  System.out.println("최대값 :" + max);
  System.out.println("평균 :" + (double) sum / numbers.length);
  ```

  > 아래와 같이 출력 됩니다.
  >
  > ![image-20231122142119363](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231122142119363.png)

  <br/>

- `for( ; ; )` : for문에 조건을 입력하지 않으면 무한루프 됩니다.

  <br/>

#### 			2.2.1. foreach문

- 복수의 데이터의 모음(배열 등)인 변수에 대하여 사용할 수 있는 특수한 형태의 반복문
- `for (<자료형> name : <배열명>) {<동작 사항>}`
- 여러개의 데이터에 같은 동작을 지시할 수 있습니다.

<br/>

- 아래의 for문을 foreach문으로 바꿔보겠습니다.

  ```java
  String[] myHome = {"me", "meow", "computer"};
  for (int i = 0; i < myHome.length ; i++) {
      String name = myHome[i];
      System.out.println(name);
  }
  ```

  > 아래와 같이 출력 됩니다.
  >
  > ![image-20231122144430968](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231122144430968.png)

  <br/>

- foreach문으로 나타내면 아래와 같습니다.

  ```java
  String[] myHome = {"me", "meow", "computer"};
  for (String name : myHome) {
      System.out.println(name);
  }
  ```

  > 아래와 같이 출력 됩니다.
  >
  > ![image-20231122144430968](231122%20%EC%A0%9C%EC%96%B4%EB%AC%B8%20(Control%20Statements).assets/image-20231122144430968-1700631909366-1.png)


#### <br/>		2.2.2. for문 연습 문제 풀이

- 아래는 for 연습문제 중 답을 내지 못한 문제인데 다시 한번 확인해보겠습니다.

  > 정수 n이 입력된 뒤, n개의 이름이 
  >
  > 개행을 기준으로 입력이 된다고 가정할 때, 
  >
  > n개의 이름을 입력된 순서의 반대로 출력하여라.

  ```java
  Scanner sc = new Scanner(System.in);
  //3
  //Alex Rodz
  //Brad
  //Chad
  int n = sc.nextInt();
  // 정수 입력 이후 개행 소모 용도
  sc.nextLine();
  
  String[] names = new String[n];
  // n개의 이름 입력 받기
  for (int i = 0 ; i < n ; i++){
      names[i] = sc.nextLine();
  }
  //이 시점에서 모든 이름을 받은 상태이다.
  
  for (int i = 0 ; i < n ; i++){
      // 0 ~ n - 1까지 n개 이므로
      // 제일 뒤에 있는 애는 n - 1에 있다
      System.out.println(names[n - i - 1]);
  }
  ```

  <br/>

  <br/>

### 2.3. 반복문 제어

- 특정 상황에서 반복을 중단하거나, 일부 코드를 실행하고 싶지 않을 때 반복문을 제어합니다.

#### 		2.3.1. break문

- 반복문 수행 중 반복문을 중단

  ```java
  numbers = new int[]{1, 3, 4, 11, 19, 21, 23};
  int target = -1;
  for (int i = 0; i < numbers.length; i++) {
      if (numbers[i] == 19) {
          target = i;
          //발견 즉시 반복 종료
          break;
      }
  }
  System.out.println(target);
  ```

<br/>

#### 		2.3.2. while문

- 반복문 수행 중 반복문을 중단

#### 

