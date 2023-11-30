# Stream API

## 1. Stream 개요

### 1.1. Stream

- 인터페이스를 통해 컬렉션 사용을 표준화 하기는 했지만
- 컬렉션 클래스에는 같은 기능의 메서드들이 중복해서 정의되어 있습니다.
- 또한 반복문 (for, Iterator)을 이용하여 데이터를 다룹니다.

<br>

- 이를 해결하기 위한 방법으로

- 다양한 데이터 소스를 표준화된 방법으로 다루기 위한 방식인 Stream을 만들었습니다.

- 데이터 소스를 추상화하고

- 데이터를 다루는데 자주 사용되는 메서드들을 정의해 놓았습니다.

- 이를 통해 데이터를 저장하지 않고 데이터가 하나씩 나와서 함수의 목록을 거쳐 결과 데이터를 만들어내는 방식으로 동작합니다

  <br>

  <br>

### 1.2. Stream의 특징

1. 데이터 소스를 변경하지 않습니다.
2. 일회용 입니다.
3. 작업을 내부 반복으로 처리합니다.
4. 최종 연산까지 중간 연산이 수행되지 않습니다. (✅지연된 연산)

<br>

<br>

### 1.3. Stream 사용법

1. **Stream 만들기**

   - Collection 인터페이스의 메서드를 사용합니다.

   ```Java
   Stream<E> stream()
   ```

   - List를 Stream으로 생성하는 예시를 만들어보겠습니다.

   ```java
   List<Integer> List = Arrays.asList(매개변수);
   ```

2.  **중간연산 (Intermeditate Operation) : Stream에 적용할 작업 전달**

   - Stream을 정렬합니다.

   ```java
   Stream<Integer> intStream = list.stream();
   ```

3.  **최종연산 (Terminal Operation) : Stream 결과 누합**

   - Stream의 foreach() 메서드를 적용합니다.
   - 그리고 출력합니다.

   ```java
   intStream.forEach(System.out::println); //매개변수
   intStream.forEach(System.out::println); //error : Stream이 닫혔습니다.
   ```

<br>

- 아래의 예시 코드로 알아보겠습니다.

  - <1> name를 List로 받고, 
  - <2> name에 a가 들어있는 데이터를 모아 다시 Liste로 받고,  
  - <3> 이것을 정렬하고
  - <4> 정렬된 List를 받아 출력합니다.

  ``` java
  List<String> nameList = new ArrayList<>();
  
  // ...
  
  List<String> namesWithA = new ArrayList<>();
  for (String name : nameList) {
      if (name.contains("a")) namesWithA.add(name);
  }
  namesWithA.sort(String.CASE_INSENSITIVE_ORDER);
  System.out.println(namesWithA);
  ```

  

- 상기 코드를 Stream을 활용하여 정리할 수 있습니다.

  - <1>  name를 List로 받고, 
  - <2> **.filter()** : name에 a가 들어있는 데이터를 모아 다시 Liste로 받고,  
  - <3> **.sotred()** : 이것을 정렬하여 
  - <4> **.toList()** : 정렬된 List를 반환합니다.

  ```java
  List<String> namesWithA = nameList.stream()
          .filter(name -> name.contains("a"))
          .sorted()
          .toList();
  ```

  📌이제 Stream이 종료됐습니다. 

  새로운 데이터 모음을 바탕으로 결론을 내렸습니다.

  해당 Stream 객체는 다시 호출이 불가합니다.

  <br>

  <br>

  <br>

### 1.4. 타입별 Stream

```java
Stream<String> nameArrStream = Arrays.stream(nameArray);
```

#### 1.4.1. 원시타입 스트림

```
int[] intArray = {1, 23, 14, 53, 22, 15, 10, 6};
IntStream intStream = Arrays.stream(intArray);
```

#### 1.4.2. 문자열 스트림

```
String email = "junpyo@gmail.com";
IntStream charStream = email.chars();
```

#### 1.4.3. 컬렉션 스트림 (Collection.stream())

```
List<String> nameList = new ArrayList<>();
nameList.add("구준표");
nameList.add("윤지후");
nameList.add("송이정");
nameList.add("송우빈");
Stream<String> nameListStream = nameList.stream();
```



### 1.5. Stream의 메서드

- filter() : 전달받은 함수 (stream 내 데이터)에 필터링(참인 데이터만 선별) 하는 작업입니다.

  - 기준을 사용자가 전달해야 합니다

  ```
  .filter(name -> name.contains("구"))
  ```

  <br>

- map() : 데이터를 전달 받아 새로운 데이터로 반환합니다.

  ```
  .map(name -> name.toUpperCase())
  .map(name -> {
      String nameLower = name.toLowerCase();
      String nameUpper = name.toUpperCase();
      return nameLower + nameUpper;
      })
  .map(name -> name.length())
  ```

  <br>

- sorted() : 데이터를 받아 전달받은 기준으로 정렬합니다.

  ```
  .sorted(Comparator.reverseOrder())
  ```

  <br>

- foreach() : 남은 데이터를 각각 전달받은 함수의 인자로 전달합니다.

  ```
  .forEach(System.out::println)
  ```

  <br>

- toList() : 데이터를 새로운 리스트로 만들어서 반환합니다.

  ```
  .toList();
  ```

- allMatch(), anyMatch, nonMatch : 전달받은 함수를 바탕으로, 

  - 전체가 참인지
  - 하나라도 참인지
  - 전혀 참이 없는지를
  - boolean으로 반환합니다.

  ```
  .allMatch(name -> name.length() >=4 )
  .anyMatch(name -> name.length() > 5 )
  .nonMatch(name -> name.length() < 3 )
  ```



- 메서드들을 활용하여 아래 문제를 풀어보겠습니다

  ```
  이름들중에서
  길이는 5 이상이며
  대문자 C가 들어있으며
  d가 포함되어있지 않은지 확인하라
  ```

  - 아래와 같이 표현할 수 있습니다.

  ```java
  nameListStream = nameList.stream();
  boolean result = nameListStream
          .filter(name -> name.length() >= 4)
          .filter(name -> name.contains("A"))
          .noneMatch(name -> name.contains("b"));
  System.out.println(result);
  ```