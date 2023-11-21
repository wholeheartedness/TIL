# 변수(Variable)와 자료형

## 📌1. 변수 : 값을 저장하는 기억공간(데이터를 담는 상자)

- 자료형 : 변수의 타입(상자의 구분)\

- 식별자 : 변수의 이름 (상자명)

​		변수는 아래와 같이 선언한다.

```java
자료형 이름 = 값;
```

- 변수 사용 시 값을 **재사용**할 수 있음

### 1.1 변수 선언 시 주의할 점

- 값은 자료형과 일치해야 한다
- 이름은 중복될 수 없다

### 	1.2 변수 이름 짓는 방법

1. 숫자로 시작할 수 없다 (1st ❌)
2. _와 $ 외 특수문자를 사용할 수 없다 (percent% ❌)
3. int, class, return등의 예약어를 사용할 수 없다 (int int ❌)
4. Naming Convention을 준수한다 (ex. Camel Case)

## 📌2. 자료형

<img src="https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231120141552341.png" alt="image-20231120141552341" style="zoom: 67%;" />

### 	2.1 문자형 자료형

```java
//작은 따옴표를 씀 ''
char charactor = 'a';
char digit = '1';
//char isString = "1" //error: 한글자라도 큰따옴표는 문자열
//문자열은 String(참조형)
String line = "Hello Java";
```

### 	2.2 정수형 자료형

```java
int integer = 10;
//int와 long 구분을 위해 long은 끝에 L을 입력한다.
long longInteger = 100000000000L;
short smallInteger = 10000;
byte reallySmallinteger = 127;
```

### 	2.3 실수형 자료형	

```java
//float와 double 구분을 위해 float는 끝에 F를 입력한다.
float floatPoint = 2.718F;
//거의 double만 쓴다. (유효수가 커서 정교함)
double doublePoint = 3.13159265359;
//진짜 긴 소수는?
double longPi = 3.14159265358979323846;
System.out.println(longPi); //3.141592653589793
```

### 	2.4 논리형 자료형

```java
boolean success = false;
boolean willSuccess = true;
success = true; 
System.out.println(success); //true
```



### 3. 문자열 표현하기

#### 3.1. Escape Sequence

- `"Say Something"`을 문자열로 표현하고 싶다면?

  ➡️백슬래시 (\\)를 사용하여 Escape Sequence를 활용할 수 있습니다

  ```java
  String sentence = "\"Say Something\" 이렇게 작성하면 됩니다.";
  ```

  > 아래와 같이 출력 됩니다.
  >
  > ![image-20231120151404825](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231120151404825.png)

- 다음줄 : \n

- 탭 : \t

- 캐리지 리턴: \ r

- 백스페이스: \b

  ```java
  System.out.println("개행문자\n아랫줄에 표현됩니다.");
  System.out.println("name\t 이구월");
  System.out.println("Age\t 3년 정도");
  System.out.println("character\t 귀여움");
  System.out.println("캐리지리턴\r이겁니다");
  System.out.println("백스페이스\b한글자를 지웁니다");
  
  ```

  > 아래와 같이 출력 됩니다.
  >
  > ![image-20231120152410159](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231120152410159.png)



#### 3.2. 문자열 포맷팅 (String Formatting)

- 포맷 코드 : 어떤 자료형의 데이터가 표현될 지를 문자열로 내부에 지정하는 방법

  ![image-20231121160140509](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231121160140509.png)

  ```java
  int tall = 168;
  String status = "평균 이상";
  String messageTemplate = "사용자 키: %d (%s)";
  System.out.println(String.format(messageTemplate, tall, status));
  ```

  > 아래와 같이 출력 됩니다.
  >
  > ![image-20231120153331200](231120%20%EB%B3%80%EC%88%98(Variable)%EC%99%80%20%EC%9E%90%EB%A3%8C%ED%98%95.assets/image-20231120153331200.png)

#### 3.3. 배열

📌배열 : 하나의 변수에 여러 데이터를 정리하여 저장하기 위해 사용

- 대괄호([ ])를 사용하여 배열을 선언하고 중괄호({ })로 배열 아이템을 작성합니다.

  ```java
  자료형[ ] 변수명 = {아이템1, 아이템2, 아이템3...};
  ```

- 변수를 가져올 때는 대괄호([ ])를 이용하며, [ ] 안에 가져올 아이템 번호를 작성합니다. 

  ```java
  변수명[아이템번호];
  ```

- 변수에 값을 할당할 때에도 [아이템번호]를 사용할 수 있습니다.

  ```java
  변수명[아이템번호] = 21;
  ```

  
