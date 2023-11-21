# 연산자(Operator)

## 1. 연산자 개요

📌연산자 (Operator) : 어떤 기능을 수행하는 기호 (+. -, *, / ...)

📌피연산자(Operand) : 연산자의 작업 대상(변수, 상수, 리터럴, 수식)

## 2. 연산자의 종류

### 2.1. 연산자 우선순위

```java
// 사칙연산의 우선순위
int result = 10 + 5 * 3;
System.out.println(result);      // 25
// 괄호가 최우선
result = (10 + 5) * 3;
System.out.println(result);     // 45
// %의 우선순위는?
result = (10 + 5 % 3) / 3 + 2 * 3;
System.out.println(result);     // 10
```

### 2.2. 산술 연산자

![image-20231121103905412](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231121103905412.png)

```java
public static void main(String[] args) {
    int plus = 10 + 20;             // 30
    int minus = 20 - 10;            // 10
    int multiply = 20 * 10;         // 200
    int divide = 20 / 10;           // 2 // 💡정수/정수 = 실수가 나올 수도 있으나 정수로 나옴
    int modulo = 15 % 10;           // 5
    System.out.println(plus);
    System.out.println(minus);
    System.out.println(multiply);
    System.out.println(divide);
    System.out.println(modulo);
```

```java
// dive 에러 처리해보기 (실수 출력)
// ❌1. 데이터를 받는 애를 int가 아니라 double로 해보자
double doubleDivide = 21 / 10; // 2.0
System.out.println(doubleDivide);
// ⭕2. 나누기 전에 실수의 연산이라고 정의
// 피연산자 중 하나라도 Double이면 결과도 double
doubleDivide = 21.0 / 10;
System.out.println(doubleDivide); // 2.1
```

#### 	2.2.1.형변환 (Type Casting)

- 실수 결과를 정수에 넣을 수 있을까?

  ```java
  int example = 21.1 / 10.2;
  ```

  ➡️ 형변환 : 상황에 따라 적당한 자료형이 되도록 형태를 바꿔줌

- 묵시적(implicit) 형변환: 자동 변환되는 데이터(작은 것을 큰 것에 넣을 때)

  ```
  byte -> short -> int -> long -> float -> double
  ```

  - int -> long
  - float -> double
  - byte -> int 
  - ...

- 명시적(explicit) 형변환: 수동으로 변환하는 데이터(큰 것을 작은 것에 넣을 때)

  ```java
  int intResult = (int) 21.1;
  System.out.println(intResult);
  ```

  - 형변환을 연산에서 사용해보기

  ```java
  int intInputF = 21;
  int intInputS = 10;
  double inputResult = intInputF / intInputS; // ❌2.0
  System.out.println(inputResult);
  inputResult = (double) intInputF / intInputS; // ⭕2.1
  System.out.println(inputResult);
  ```

- char형 형변환

  ```java
  int asciiA = 65;
  System.out.println((char) asciiA); // A
  System.out.println((char) (asciiA + 10)); // K
  ```

#### 		2.2.2. 문자열 덧셈(String Concatenation)

  ```java
System.out.println("여기에 10을 입력하시오: " + 10);
System.out.println(10 + " + " + 10 + " = " + 20 );
String formula = 10 + " + " + 10 + " = " + 20;
  ```

  ```
int date = 5;
System.out.println("Today is" + date + "th of July")
  ```

- 여기서 Date에 할당된 변수 자체가 형변환 대상은 아닙니다.



#### 		2.2.3. 증감 연산자

- 대상 피연산자의 값을 1 증가 or 감소

- 단한 연산자 -> 피연산자가 1개

- 반복 작업에서 반복 횟수

- 배열에서 다음 대상을 나타내는 index

- 횟수 세는 용도

  ```java
  //전치 계산
  ++변수 ;
  --변수 ;
  //후치 계산
  변수++ ;
  변수-- ;
  ```

  - ✅전치계산: 앞에 있으면 count 1 증가하고 줄 실행
  - 후치계산: 뒤에 있으면 줄이 실행 되고 난 뒤 count 1 증

  ```java
  count = 10;
  System.out.println(++count); // 11 (출력 전에 1 증가, 값 11)
  System.out.println(count++); // 11 (출력 후에 1 증가, 값 12)
  System.out.println(--count); // 11 (출력 전에 1 감소, 값 11)
  System.out.println(count--); // 11 (출력 후에 1 감소, 값 10)
  System.out.println(count); // 10
  ```

#### 		2.2.4. 복합 할당(대입) 연산자

- 할당 연산자(=)와 다른 산술 연산자를 합친 연산자

- 오른쪽 피연산자의 값을 왼쪽 피연산자와 계산 후 할당

  ![img](https://mblogthumb-phinf.pstatic.net/MjAxOTA1MTlfNjUg/MDAxNTU4MjQ3Mjg2MTU4.l9k8zeX00sPGZ9Z7ePgLstpcLf8S86Q2vgTGOQpW4okg.x24nUcsOlrx9pX_Pg1EjZtuABBSFuyG7kteCJHD4khsg.PNG.yiyb0603/캡처.PNG?type=w800)

  ```java
  //복합 할당 연산자
  int addTo = 1;
  addTo += 10;                //addTo = addTo + 10
  System.out.println(addTo);  // 11
  addTo *= addTo;             //addTo = addTo * addTo
  System.out.println(addTo);  // 121
  addTo /= 12;                //addTo = addTo / 12
  System.out.println(addTo);  //10
  addTo %= 10;                //addTo = addTo % 10
  System.out.println(addTo);  //0
  addTo -= 20;                //addTo = addTo  20
  System.out.println(addTo);  //-20
  addTo *= -1;                //addTo = addTo * -1
  System.out.println(addTo);  //2-
  ```

### 2.3. 비교 연산자

- 두 피연산자의 대소를 비교하여 **boolean**을 반환

- "같다" 보다는 "같냐?"

  ![img](https://t1.daumcdn.net/cfile/tistory/99E7FB335A16B7AB29)

  ```java
  //비교 연산자
  int small1 = 10;
  int small2 = 20;
  int big = 91;
  double bigD = 91.0;
  System.out.println(small1 == small2); // true
  System.out.println(big == small2); // false
  System.out.println(big == bigD); // true 형이 다르더라도 실제 값이 얼마냐에 따라 동작함
  System.out.println(small1 > small2); // false
  ```

- 두 정수 A와 B가 입력될 때,
  A의 세제곱이 B의 제곱보다 크면 true, 아니면 false를
  boolean 변수를 선언하지 않고 출력하여라.

  ```java
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      int a = sc.next();
      int b = sc.next();
      System.out.println(a*a*a > b*b);
  }
  ```

#### 2.3.1. 논리 연산자

- 두가지 조건(boolean)에 대하여, 두 조건의 참/거짓의 조합에 따라 boolean 결과를 반환

- 논리 연산

- "둘 다", ""둘 중 하나라도""

- !(Not) -> &&(And) -> ||(Or)

  ![image-20231121141707229](C:/Users/mmm58/AppData/Roaming/Typora/typora-user-images/image-20231121141707229.png)

  ```java
  // 체온은 37 이하 이면서 나이는 20 이상 : 입장 가능
  int temp = 36;
  int age = 21;
  // 체온은 37 이하
  boolean notSick = temp <= 37;
  // 나이는 20 이상
  boolean isOfAge = age >= 20;
  // 입장 가능한가?
  boolean canIn = notSick && isOfAge;
  System.out.println(canIn); // true
  ```

### 2.4. 비트 연산자

- 데이터를 비트 단위로 계산하는 연산자

- 데이터에 저장된 비트를 기준으로 계산

  ```java
  //ex
  //11 -> 1101
  //05 -> 0101
  //각 비트 자리수를 비교하여 연산
  ```

- **AND 연산(&)**

  - 두 비트가 모두 1 ==>  1
  - 두 비트중 하나라도 0 ==> 0

  ```java
  // 비트연산 AND (&)
  System.out.println(11 & 5); // 1 = 0000 0001
  ```

- **OR 연산(|)**

  - 두 비트가 하나라도 1 ==> 1
  - 두 비트가 모두 0 ==> 0

  ```java
  // 비트연산 OR (|)
  System.out.println(11 | 5); // 15 = 0000 1111
  ```

- **XOR 연산(^) (Exclusive OR)**

  - 두 비트가 서로 다르면 ==> 1
  - 두 비트가 서로 같으면 ==> 0

  ```java
  // 비트연산 XOR (^)
  System.out.println(11 ^ 5); // 14 = 0000 1110
  ```

- **NOT 연산(~)**

  - 각 비트를 반대로 변환
  - 1 ==> 0 , 0 ==> 1

  ```java
  // 비트연산 NOT (~)
  System.out.println(~11); // -12 = 1111 0100
  System.out.println(~5); // -6 = 1111 1010
  ```

- **SHIFT 연산 (<<, >>, >>>)**

  - 비트를 왼쪽/오른쪽으로 이동

  - 왼쪽  피연산자를 오른쪽 숫자만큼 이동

  - 비트 범위를 넘어가면 버림

    ![image-20231121152840296](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231121152840296.png)

  - **LEFT SHIFT 연산  (<<)**

    - 비트를 왼쪽으로 이동
    - 비어버린 비트는 0으로 채움

  - **RIGHT SHIFT 연산 1 (>>)**

    - 비트를 오른쪽으로 이동
    - 비어버린 비트는 부호를 유지
    - **본래 왼쪽 비트가 1이면 1로, 0이면 0으로 채움**

  - **RIGHT SHIFT 연산 2 (>>>)**

    - 비트를 오른쪽으로 이동
    - **비어버린 비트는 0으로 채움**

  ```
  // 12 = 0000 1100
  System.out.println(12 << 2); // 48 = 0011 0000 (*2*2)
  System.out.println(12 >> 1); // 6 = 0000 0110 (/2)
  System.out.println(-12 >> 1); // -6 = 1111 1001 (*2)
  System.out.println(-12 >>> 1); // 2147483642 = 0111 1001
  ```

### 2.5. 삼항 연산자 (Ternary Operator)

- 하나의 조건에 대해 참/거짓에 따라 두가지 값 중 하나를 결정

- 조건 하나, 후보 값 2개 => 총 3개의 항 필요

  ```java
  boolean ? (참일 때 결과) : (거짓일 때 결과)
  ```

  ```java
  int temperature = 37;
  String msg = temperature < 38 ? "OK" : "Sick"; //OK
  ```

  ```java
  //미세먼지 수치
  Scanner sc = new Scanner(System.in);
  int dust = sc.nextInt();
  // 80이하면 "좋음", 아니면 "나쁨"
  String message = dust <= 80 ? "좋음" : "나쁨";
  System.out.println(String.format("미세먼지 수치: %d, (%s)", dust, message));
  ```

- 강력! 유용! 하지만 지나치면 가독성이 저하됩니다.

