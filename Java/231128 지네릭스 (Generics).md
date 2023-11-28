# 지네릭스 (Generics)

<br/>

## 1. Generic Type Reference

- 컴파일 시 타입을 체크해주는 기능 입니다.

  - 타입 자체를 변수로 받는 기능이라고도 합니다.

- 클래스, 인터페이스, 메서드를 좀 더 일반적인 상황에서 활용하고 재사용성을 높이는 방법입니다.

  - 객체의 타입 안정성을 높이고 형변환의 번거로움을 줄여줍니다

    **<br>**

  **💡 Generics의 장점**

  1. 타입의 안정성을 제공합니다.
  2. 타입 체크와 형변환을 생략할 수 있으므로 코드가 간결해 집니다.

<br>

- 예시 코드로 알아보겠습니다.

  ```java
  public class IntArrayWrapper {
      private final int[] intArray;
  
      public IntArrayWrapper(int[] intArray) {
          this.intArray = intArray;
      }
  
      // 1. intArray의 길이를 반환하는 메서드
      public int intArrayLength(int[] intArray) {
          return this.intArray.length;
      }
  
      // 2. 주어진 int target이 intArray에 존재하는지 반환하는 메서드
      public boolean isTargetIn(int target) {
          for (int number : this.intArray) {
              if (target == number) return true;
          } return false;
      }
  
      // 3. 주어진 intArray에서 최댓값을 찾는 메서드
      public int max() {
          int max = this.intArray[0];
          for (int number : this.intArray) {
              max = Math.max(number, max);
          } return max;
      }
  }
  ```

  - int[] intArray의 자료형을 Double로 바꾸고 싶을 때, 일일이 바꾸어주어야 하는 번거로움이 있습니다.
  - 이 때 사용자가 자료형을 임의로 선택할 수 있는 것을 지네릭스라고 합니다.

  <br>

- 클래스를 작성할 때, Object 타입 대신 변수 T(Type Parameter)를 사용합니다. (Java 5버전 이후)

- <T> ➡️ T를 타입처럼 사용할 수 있습니다.

  ```java
  public class ArrayWrapper<T> {
  
      private T[] array;
  
      public ArrayWrapper(T[] array) {
          if (array == null)
              throw new IllegalArgumentException("null array provied");
          this.array = array;
      }
      
      public int length() {
          return array.length;
      }
      
      public boolean contains(T target){
          for (T item : this.array) {
              if (item == null) continue;
              if (item.equals(target)) return true;
          } return false;
      }
  }
  ```

- main 문에서는 아래와 같이 사용합니다.

  ```java
  public static void main(String[] args) {
      Integer[] intArray = {10, 20, 30};
      ArrayWrapper<Integer> integerArrayWrapper= new ArrayWrapper<>(intArray);
      Double[] doubleArray = {1.0, 2.0, 3.0};
      ArrayWrapper<Double> doubleArrayWrapper = new ArrayWrapper<>(doubleArray);
  ```

  ---

- 메서드에서 사용 시 `제어자 뒤 <T> 반환 타입 전` 로 선언을 해줍니다.

  ```java
  public static <T> boolean contains(T[] source, T target) {
      for (T item : source) {
          if (item == null) continue;
          if (item.equals(target)) return true;
      } return false;
  }
  ```

- main문에서 source에 어떤 타입형의 배열을 넣고, 어떤 타겟을 지정해도 자동으로 형변환이 되어 연산합니다.

  ```java
  System.out.println(contains(doubleArray, 2.0)); //true
  System.out.println(contains(intArray, 25)); //false
  ```

  

<br>

---

### 1.2. Comparable

- 구현하는 인터페이스에 타입 파라미터를 전달하면 
- 오버라이딩 하는 메서드에서 타입을 명시하기 좋습니다.

- 아래 예시코드로 알아보겠습니다.

  ```java
  public class Person {
      private String name;
      private int age;
      public Person() {}
  }
  ```

- Comparable 을 사용하여 형변환을 해보겠습니다.

  ```java
  public class Person implements Comparable<Person>{
      private String name;
      private int age;
  
      // 구현하는 인터페이스에 타입 파라미터를 전달하면
      // 오버라이딩 하는 메서드에서 타입을 명시하기 좋다.
      @Override
      public int compareTo(Person other){
          return this.age - other.age;
      }
  
      public Person() {}
  }
  ```

  ---

  

- 지네릭스를 사용하여 최댓값을 구하는 방법은?

  ```java
  public T max() {
      T max = this.array[0];
      for (T item : this.array) {
          if (max == null) max = item;
          // 비교가 가능해야한다.
          max = Math.max(item, max); //error
      }
  }
  ```

- 비교가 가능해야 하지만, 비교가 불가능한 경우가 있습니다. (String 등)

- 이럴 때는 형변환 할 수 있는 객체의 타입을 지정해줄 수 있습니다.

  ➡️ <T extends Comparable<T>> 을 사용합니다

- 자신과 비교될 수 있는 모든 타입 T라고 지정해줍니다.

  ```java
  public class ArrayWrapper<T extends Comparable<T>> {}
  ```

- 이제 비교가 가능합니다.

  ```java
  public T max() {
      T max = this.array[0];
      for (T item : this.array) {
          if (item == null) continue;
          if (max == null) max = item;
          // 비교가 가능해야한다.
          else if (item.compareTo(max) > 0) max = item;
      } return max;
  }
  ```

  ---

- <T>를 해주면 T를 타입처럼 쓸 수 있습니다.

  ```java
  public class ArrayWrapper<T
          extends Number & Comparable<T> & Serializable>
  {
  ```

---

## 2. Optional