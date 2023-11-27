# String 및 Wrapper Class

## 1. String과 래퍼클래스 개요

- String은 참조 타입입니다.
  - 메서드(String.format 등)가 있는 이유입니다.
- 배열도 참조 타입입니다.



## 2. 원시타입 래퍼 클래스 (Wrapper Class)

- 기본 타입의 데이터를 객체로 취급해야 하는 경우가 있습니다.

  - ex. 메소드의 인수로 객체 타입만 요구하는 경우

- 이 때 기본 타입 데이터를 객체로 변환 후 작업을 수행해야 합니다.

-  JVM이 객체지향 관점에서 사용할 수 있는 `Wrapper Class`를 제공합니다.

  ![img](https://velog.velcdn.com/images%2Fdoxxx93%2Fpost%2F4e189512-4f8a-4ebb-825f-66e4151bb87c%2Fimage.png)

- 8개 기본 타입에 해당하는 데이터를 객체로 포장해줍니다.

- java.lang 패키지에 포함되어 제공합니다.

### 2.1 래퍼클래스의 특징

1. 참조 타입이지만, String처럼 값을 할당 가능합니다.

   ```java
   String string = "";
   int primInt = 10;
   Integer refInt = 10;
   
   ```

   <br/>

2. 서로 상호 호환이 됩니다.

   ```java
   refInt = primInt;
   primInt = refInt;
   ```

   <br/>

3. 사칙 연산도 그냥 참조 타입을 바탕으로 사용 가능합니다.

   ```java
   refInt *= 10;
   System.out.println(refInt);
   refInt /= primInt;
   System.out.println(refInt);
   
   Long refLong = 100000000L;
   refLong *= 2;
   System.out.println(refLong);
   
   Character a = 'a';
   ```

<br/>

<br/>

### 2.2. 래퍼클래스의 단점

1. Heap 메모리를 참조합니다 ➡️ 성능 문제를 야기합니다.

   <br/>

   <br/>

### 2.3. 래퍼 클래스를 활용한 유용한 기능

1.  문자열을 정수로 반환

   ```java
   Integer parsedInt = Integer.parseInt("1000");
   System.out.println(parsedInt + 100); //1100
   ```

   <br/>

2. 문자열을 실수로 반환

   ```java
   Double parsedDouble = Double.parseDouble("1.0");
   System.out.println(parsedDouble); //1.0
   parsedDouble = Double.parseDouble("3.141592");
   System.out.println(parsedDouble); // 3.141592
   ```

   <br/>

3. 정수의 최댓값과 최솟값 상수 구하기

   ```java
   System.out.println(Integer.MAX_VALUE); //2147483647
   System.out.println(Integer.MIN_VALUE); //-2147483648
   ```

   <br/>

4. Long의 최댓값과 최솟값 구하기

   ```java
   System.out.println(Long.MAX_VALUE); //9223372036854775807
   System.out.println(Long.MIN_VALUE); //-9223372036854775808
   ```

   <br/>

5. Double의 최댓값과 양수의 무한대 값 구하기

   ```java
   System.out.println(Double.MAX_VALUE); //1.7976931348623157E308
   System.out.println(Double.POSITIVE_INFINITY); //Infinity
   ```

   <br/>

   <br/>

---

- 아래 문자열로 예시를 확인해보겠습니다.

```java
String sentence = " Hello, world! Have a Good Day";
```

<br/>

6. 문자열 길이 구하기

   ```java
   System.out.println(sentence.length()); // 30
   ```

   <br/>

7. 문자열 자르기

   ```java
   System.out.println(sentence.substring(10)); // rld! Have a Good Day
   System.out.println(sentence.substring(7, 12)); // worl
   ```

   <br/>

8. 문자열 나누기

   ```java
   String[] strArry = sentence.split(" ");
   for (String str : strArry) {
       System.out.println(str);
   }
   /*
       Hello,
       world!
       Have
       a
       Good
       Day
    */
   ```

   <br/>

   <br/>

---

- 아래의 문자열로 확인해보겠습니다.

```java
String email = "seojulee@naver.com";
```

<br/>

9. 특정 문자로 문자열 나누기

   ```java
   String[] emailSplit = email.split("@");
   for (String str : emailSplit) {
       System.out.println(str);
   }
   /*
       seojulee
       naver.com
    */
   ```

   <br/>

   <br/>

---

- 아래의 문자열로 확인해보겠습니다.

```java
String source = "https://wholeheartedness.tistory.com/@@123";
```

<br/>

10. 특정 문자열 찾기

    ```java
    System.out.println(source.indexOf("wholeheartedness")); //8 (문자열 8번째에 있습니다)
    ```

    <br/>

11. 문자열 한글자씩 확인하기

    ```java
    for (int i = 0; i < source.length(); i++) {
        //문자열을 배열 취급해서 [i]번째 가져오기 (문자열 번호 확인이 필요할 때)
        System.out.println(source.charAt(i));
    }
    ```

    <br/>

12. 문자열 내부에 저장된 문자 배열 반환하기 (전체)

    ```java
    for (char letter : source.toCharArray()) {
        //문자열 내부에 저장된 문자 배열 반환하기 (전체 문자열 반환하기)
        System.out.println(letter);
    }
    ```

    <br/>

13. 각 글자가 영문인지 숫자인지 확인하기

    <br/>

- 문자가 숫자를 나타내는 문자인지 확인

  ```java
  for (char letter : source.toCharArray()) {
      if (Character.isDigit(letter)) {
          System.out.println(String.format("digit: %c", letter));
      }
  }
      /*
              digit: 1
              digit: 2
              digit: 3
       */
  ```

  <br/>

- 문자가 인간의 문자를 나타내는 문자인지 확인

  ```java
  for (char letter : source.toCharArray()) {
      if (Character.isLetter(letter)) {
          System.out.println(String.format("letter : %c", letter));
      }
  }
  	/*
          letter : h
          letter : t
          letter : t
          letter : p
          letter : s
          letter : w
          letter : h
          letter : o
          letter : l
          letter : e
          letter : h
          letter : e
          letter : a
          letter : r
          letter : t
          letter : e
          letter : d
          letter : n
          letter : e
          letter : s
          letter : s
          letter : t
          letter : i
          letter : s
          letter : t
          letter : o
          letter : r
          letter : y
          letter : c
          letter : o
          letter : m
  	*/
  ```

  

