# 메서드(Methods)

💡메서드를 `레시피`에 비유해 봅시다.

- 전국 스타벅스의 맛은 똑같습니다.

- "스벅 레시피"를 공유하고 있기 때문이죠

- "new 스벅 레시피"가 생긴다면 "스벅 레시피"에 기록해두고 찾아보면 나중에 또 똑같이 만들 수 있습니다.

  <br/>

➡️ 같은 맥락에서 `코드 단위`에서 살펴보겠습니다.

- **코드를 한 곳에 모아두고 필요할 때 가서 실행하면**
- 한 번 만든 코드를 복붙하지 않아도 돼서 간단해집니다.

<br/>

<br/>

### - 그래서 함수와 메서드란?

<br/>

- `함수` : 독립적으로 실행될 수 있는 코드 조각

- `메서드` : 특정 클래스와 연결되어 그 클래스 객체에서 수행 가능한 기능

  <br/>

- 프로그래밍 패러다임이 명령형➡️절차지향 으로 넘어오면서 생긴 문법 입니다. (객체지향인 클래스의 일부)

  <br/>

  📌명령형 프로그래밍

  - 컴퓨터가 수행할 명령을 순서대로 써 놓은 프로그래밍 입니다.

    <br/>

  📌절차지향 프로그래밍

  - Procedure Call, 프로시저 호출을 바탕으로 하는 프로그래밍 패러다임 입니다.
  - 코드를 복사하는 대신 한곳에 모아둡니다.

  <br/>

  <br/>

  <br/>

## 1. 메서드(Methods) 

- 클래스 내부에서 특정 기능을 하는 코드를 한곳에 모아 실행할 수 있기 해주는 코드 묶음 

  - 작업 수행을 위한 명령문의 집합

- 일반적인 프로그래밍 언어에서 함수와 유사한 역할

  - 어떤 값을 입력 받아 처리하고 결과를 반환함

    <br/>

  📌메서드 사용의 장점

  - 반복 코드를 줄인다 -> 전체 코드 동작 흐름을 쉽게 만들어 이해를 높인다 -> 코드 관리가 용이해 진다 (분해)

  - 동작에 메서드 이름을 붙인다 -> 내용을 몰라도 동작 이해 가능 (추상화)

    <br/>

    <br/>

### 1.1. 메서드 정의

<br/>

1. 자바에서 가장 처음 작성한 코드를 살펴봅니다.

```java
public static void main(String[] args) {
    System.out.println("메인 메서드에서 실행할 코드입니다.");
}
```

>  `main 메서드`를 볼 수 있습니다.
>
> 프로그램의 시작점(Entrypoint)를 정의하는 메서드입니다.
>
> line 1은 선언부, line 2는 구현부 입니다.
>
> ![image-20231123110430160](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123110430160.png)

<br/>

2. 두개의 정수를 더하는 메서드를 정의해보겠습니다.

```java
public static int addTwoInt(int a, int b) {
    return a + b;
}
```

> `public static <자료형> <메소드 이름> (<매개변수1>, <매개변수2>) {<실행할 코드>}`
>
> 상기 방법으로 메소드를 정의합니다.
>
> 매개변수로 int a, int b를 정의했습니다.
>
> 실행 코드는 매개변수를 더한 값  return 입니다.

- ✨매개변수가 필요 없는 메서드는 비워두어도 무방합니다.

<br/>

3.  main 메소드 프로그램에 '2'에서 정의한 메서드를 추가해보겠습니다.

```java
public static void main(String[] args) {
    System.out.println("메인 메서드에서 실행할 코드입니다.");
    System.out.println(addTwoInt(10,20));
}
```

> `(<메서드 이름> (<매개변수1>,<매개변수2>)`
>
> 상기 방법으로 메서드를 호출합니다.
>
> 전체 코드를 실행하면 아래와 같이 출력됩니다.
>
>  ![image-20231123110218954](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123110218954.png)

<br/>

4.  세개의 정수를 받아서 3으로 나눈 몫을 반환하는 메서드를 만들어보겠습니다.

```java
public static int threeIntAndDivide(int a, int b, int c){
    int divide = (a + b + c) / 3;
    return divide;
}
```

<br/>

5. main 메소드 프로그램에 '4'에서 정의한 메서드를 추가해보겠습니다.
   - 할당될 매개변수를 main  메소드에서 정의해보겠습니다.

```java
public static void main(String[] args) {
    System.out.println("메인 메서드에서 실행할 코드입니다.");
    System.out.println(addTwoInt(10,20));
    int A = 1;
    int B = 2;
    int C = 3;
    System.out.println(threeIntAndDivide(A, B, C));
}
```

> 아래와 같이 출력 됩니다.
>
> ![image-20231123112040588](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123112040588.png)



### 1.2. 반환(Return)

✨**반환값이 있는 메서드**는 반드시 **return문**이 있어야 합니다.

​	(cf. 반환값이 없는 메서드 : void)

- return은 반드시 **한가지 자료형(메서드 선언부에서 정의한 자료형)**이어야 합니다.

- 반환(return)과 출력(print)는 다릅니다.

  - scanner.**nextLine()** : 문자열을 ***반환 함***
  - System.out.**pirntln()** : 출력만 하고, ***반환 없음***

- 어느 시점에서든 **return을 만나면 메소드가 종료** 됩니다.'

  <br/>

  - 아래 두개의 예시 코드를 살펴보겠습니다.

  - 첫번째 코드입니다.

    ```java
    public static int findOneReturn(int[] numbers) {
        int index = -1;
        for (int i = 0; i < numbers.length; i++) {
            // 찾았다!
            if (numbers[i] == 1) {
                index = i;
                return index;           // return을 만나 바로 종료
            }
        }
        System.out.println("for 종료");
        return index;
    }
    ```

    > 배열 numbers 안에서 1을 찾으면 배열의 순서를 index에 저장하고 바로 index를 return하여 값을 반환합니다.
    >
    > 아래와 같이 출력됩니다.
    >
    > ![image-20231123130458403](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123130458403.png)
    >
    > 반복문이 return을 만나 종료되는 동시에, 메서드도 종료되어 return 아래의 값은 출력되지 않습니다.

     <br/>

  - 두번째 코드입니다.

    ```java
    public static int findOneBreak(int[] numbers) {
        int index = -1;
        for (int i = 0; i < numbers.length; i++) {
            if (numbers[i] == 1) {
                index = i;
                break;                  // break 종료 후 아래 프린트까지 반환 가능
            }
        }
        System.out.println("for 종료");
        return index;
    }
    ```

    > 배열 numbers 안에서 1을 찾으면 배열의 순서를  index에 저장하고 break합니다. 
    >
    > 이후 for문이 끝난 후 index값을 반환합니다.
    >
    > 아래와 같이 출력 됩니다.
    >
    > ![image-20231123130446156](C:/Users/mmm58/AppData/Roaming/Typora/typora-user-images/image-20231123130446156.png)
    >
    > 단순 반복문 종료인 break를 만나 "for 종료"라는 String을 출력할 수 있습니다.

  - 두개의 예제를 보듯, return을 만나면 메소드 자체가 종료되므로 어디에서 return을 하는지가 중요합니다.

  - for문을 return으로 종료하느냐, break로 종료하느냐에 따라 출력값이 달라지므로 프로그램 내용을 정확히 파악해야합니다.

  <br/>

  <br/>

  <br/>

### 1.3. 메서드 호출

- 메서드의 이름을 가지고 호출을 합니다

- `<메서드 이름> (<매개변수1>, <매개변수2>)`

  - 매개변수의 괄호가 닫히면 메서드가 호출됩니다.

  <br/>

- 두개의 예제 메서드로 만들어진 메서드를 호출하여 재사용 해보겠습니다.

  1. 두 정수의 차의 절대값을 구하는 메서드 입니다.

  ```java
  public static int diff (int a, int b){
      int c = a - b;
      if (a-b >= 0) {
          return c;
      } else {
          return -c;
      }
  }
  ```

  2. 정수의 절대값을 구하는 메서드 입니다.

  ```java
  public static int abs(int a){
      if (a >= 0) {
          return a;
      } else {
          return -a;
      }
  }
  ```

  3. 나열된 두개의 메서드 중 'b'의 메서드를 'a'에서 호출하면 'b'를 재사용하는 것으로 코드가 간결해집니다.

  ```java
  public static int diff (int a, int b){
      return abs(a-b); // 먼저 절대값을 반환하는 메서드를 만들고 재사용할 수 있음
  }
  ```

  <br/>

  <br/>

- 배열을 출력하는 String형의 메소드를 작성해보겠습니다

  ```java
  public static void printAll(String[] strArr){
      for (String str : strArr){
          System.out.println(str);
      }
  }
  
  public static void main(String[] args){
      String[] names = {"alex", "brad", "chad"};
      String[] fruits = {"apple", "banana", "kiwi"};
      printAll(names);
      printAll(fruits);
  }
  ```

  > 아래와 같이 출력 됩니다.
  >
  > ![image-20231123134058150](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123134058150.png)

<br/>

<br/>

<br/>

<br/>

## 2. 재귀 함수

- 계승 (Factorial) : n부터 1까지의 자연수를 전부 곱한 수

  - 10! = 10 * 9 * 8 * ... * 2 * 1

  ![image-20231123134248890](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123134248890.png)

  - `f(n)`과 `f(n-1)`이라는 동일한 함수가 사용되고 있습니다.
  - 본 문제보다 작은 문제를 해결해서 답을 구할 수 있습니다.
  - f(1)과 f(0)에 도달하면 종료됩니다.

  <br/>

- factorial을 구하는 예제코드로 알아보겠습니다.

  ```java
  public static int factorial(int n) {
      // 0이거나 1이면 1을 반환한다.
      if (n == 1 || n == 0) {
          return 1;
      }
      // 아니면 n * f(n-1)을 반환한다.
      else {
          return n * factorial(n - 1); //나를 호출해서 재귀한다
      }
  }
  ```

  > f(n)이 0이나 1이면  1을 리턴하면서 종료하되, 0이나 1이 되지 않으면 else 구문으로 들어가 factorial 메서드에 매개변수로 (n-1)을 주며 스스로를 호출하여 재귀합니다.
  >
  > main 함수에서  factorial(n)을 호출하여 n에 원하는 정수를 입력하면 아래와 같이 출력됩니다. (아래의 출력은  7을 입력)
  >
  > ![image-20231123135247316](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123135247316.png)

  <br/>

  - 기본적으로 종료 조건을 상단에 쓰는 것이 best입니다. 
    - 가독성이 좋습니다.
    -  **재귀함수를 종료하는 것이 핵심**이기 때문에 좀 더 잘보이도록 작성합니다.
  - 문제를 해결하는 논리가 잘 보여 편의성이 높습니다.
    - 성능보다는 가독성과 편의성 측면에서 사용합니다.

  <br/>

  - 재귀함수를 활용하여 피보나치수열을 표현하는 코드를 작성해보겠습니다.

  ```java
  public static int 피보나치(int n){
      //very short
      if ( n < 2) return n;
      else return 피보나치(n-1) + 피보나치(n-2);
  
      //short
      if (n < 2){
          return n;
      } else {
          return 피보나치(n-1) + 피보나치(n-2);
      }
  
      //middle
      if ( n == 0 || n == 1){
          return n;
      } else if (n == 2){
          return 1;
      } else {
          return 피보나치(n-1) + 피보나치(n-2);
      }
  
      //long
      if (n == 0){
          return 0;
      } else if ( n == 1 || n == 2) {
          return 1;
      } else {
          return 피보나치(n-1) + 피보나치(n-2);
      }
  }
  ```

  > 공식에 따라 F8 = 21입니다. 8을 입력하면 아래와 같이 출력됩니다.
  >
  > ![image-20231123142534876](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123142534876.png)

<br/>

<br/>

<br/>

<br/>

## 3. 오버로딩 (Overloading)

- 아래 두개의 메서드를 살펴보겠습니다.

  ![image-20231123142742209](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123142742209.png)

  - 오른쪽 하단의 4가지 중에서 문제가 되는 무엇일까요?

    ➡️ 2번째 addInt(c,d); 입니다.

  - int는 4byte, long은 8byte 자료형입니다.

  - int 매개변수를 받아 합을 구하는 `메서드 addInt` 에서 

  - `long인 매개변수 c와 d`를받아 합을 구했습니다.  

  - 매개변수 c와 d는 `메서드 addInt`의 자료형을 넘습니다.

<br/>

- 아래의 메서드를 살펴보겠습니다.

  1. 같은 기능을 하지만 매개변수의 자료형만 다른 두 메서드가 있습니다.

  ```java
  public static int add(int a, int b){
      return a + b;
  }
  
  public static long add(long a, long b){
      return a + b;
  }
  ```

  2. main 함수에서 매개변수 `intA, intB` 를 사용하여 add 함수를 호출해보겠습니다.

  ```java
  int intA = 2, intB = 3;
  System.out.println(add(intA, intB));
  ```

  > 주어진 `매개변수의 자료형(int)` 를 보고 메서드는 자동으로 일치하는 메소드를 호출합니다.
  >
  > ![image-20231123144447029](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123144447029.png)
  >
  > 마찬가지로 매개변수 `longA, longB`를 사용하면 하단 long 형의 메소드 add가 사용됩니다.

  <br/>

- 아래의 코드를 마지막으로 알아보겠습니다.

  ```java
  public static int avg(int[] intNums) {
      int sum = 0;
      for (int number : intNums) {
          sum += number;
      }
      return sum / intNums.length;
  }
  public static long avg(long[] longNums) {
      int sum = 0;
      for (long number : longNums) {
          sum += number;
      }
      return sum / longNums.length;
  }
  public static double avg(double[] doubleNums) {
      int sum = 0;
      for (double number : doubleNums) {
          sum += number;
      }
      return sum / doubleNums.length;
  }
  
  public static void main(String[] args) {
      int[] intNums = {1, 2, 3};
      long[] longNums = {2, 4, 6};
      double[] doubleNums = {1, 3, 5};
      System.out.println(avg(intNums));
      System.out.println(avg(longNums));
      System.out.println(avg(doubleNums));
  }
  ```

  > main메소드에서 호출된 메소드들을 확인해보겠습니다.
  >
  > ⬇️ 매개변수로 intNums 배열을 가질 때
  >
  > ![image-20231123151128111](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123151128111.png)
  >
  > ⬇️ 매개변수로 longNums 배열을 가질 때
  >
  > ![image-20231123151154093](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123151154093.png)
  >
  > ⬇️ 매개변수로 doubleNums 배열을 가질 때
  >
  > ![image-20231123151217344](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123151217344.png)
  >
  > 메소드의 이름이 같아도 매개변수의 자료형에 따라 각각 다른 메소드가 호출됨을 확인할 수 있습니다.

  <br/>

- 단,  메소드명과 매개변수가 같고 return 값이 같은 경우는 부적합합니다.

  ![image-20231123151525173](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123151525173.png)

  - 매개변수를 가지고 메서드를 호출 했을 때, 어떤 메서드를 호출하는 것인지는 선언부에서 확인할 수 있습니다.
  - 선언부를 구분하지 못하면 구현부로 들어가지 못하기 때문에 return값 또한 지정하지 못합니다.

  <br/>

  <br/>

  <br/>

  <br/>

## 4. 가변 인자(Varargs)

<br/>

### 4.1. 가변인자의 개요

💡String.format()의 메서드는 매개변수가 몇개 일까요?

- String.format()에는 매우 많은 매개변수가 들어갈 수 있습니다.

  - %d, %s, %f..... 사용자가 호출하는 만큼 가능합니다.

- 이럴 경우에는 어떻게 매개변수 개수를 지정할까요?

- String format의 선언문을 확인해보겠습니다.

  ![image-20231123152322158](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123152322158.png)

<br/>

- `가변인자 (Variable-length arguments lists)`

- 임의 갯수의 인자를 받을 수 있는 기능입니다.

  - 메서드 내부에서는 배열처럼 활용할 수 있습니다

  <br/>

- 아래와 같이 사용 가능합니다.

  ```java
  public static int varargAvg(int... ints){
      int sum = 0;
      for (int i = 0 ; i < ints.length ; i++){
          sum += ints[i];
      }
      return sum / ints.length;
  }
  ```

  - 매개변수 int[] ints는 원하는 만큼 지정해줄 수 있습니다.

  - main 메서드에서 호출해보겠습니다.

  ```java
  System.out.println(varargAvg(1,2,3,4,5));
  System.out.println(varargAvg(10,11,12));
  ```

  > 매개변수 인자를 몇개를 넣든 상관없이  varargAvg 메서드의구현부가 실행됩니다.
  >
  > (intelli J IDE에서는 아래와 같이 표시됩니다)
  >
  > ![image-20231123153041899](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123153041899.png)
  >
  > 아래와 같이 출력 됩니다.
  >
  > ![image-20231123153303660](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123153303660.png)

  <br/>

  - 배열도 전달이 됩니다

  ```java
  int[] argList = { 1, 2, 3, 4, 5, 6, 7, 8};
  System.out.println("avg of 1~8 :" + varargAvg(argList));
  ```

  > 아래와 같이 출력 됩니다.
  >
  > ![image-20231123153325863](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123153325863.png)

  <br/>

  💡단, 가변인자는 가장 뒤쪽에 넣습니다.

  - 가변인자를 앞쪽에 넣으면 어디까지가 가변인자 인지 알 수 없기 때문입니다.

  <br/>

  - 아래의 예시를 살펴보겠습니다.

  ![image-20231123153512701](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123153512701.png)

  ![image-20231123153524090](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123153524090.png)

  >  가변인자와 offset을 컴퓨터가 임의로 지정했습니다. 

  <br/>

  💡 메서드 오버로딩과 함께 사용할 시 주의합니다.

  ![image-20231123153851328](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231123153851328.png)

  - 배열로 가변인자 전달이 가능한 경우도 있기 때문에
  - 두 개가 동시에 있을 때, 매개변수의 형태가 모호해집니다.
  - 이럴 경우 컴파일 에러가 발생합니다.