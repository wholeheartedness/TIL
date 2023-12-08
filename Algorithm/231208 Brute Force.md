# [알고리즘] Brute Force

- 알고리즘 적으로 가능한 모든 답을 검사하는 방식의 알고리즘 풀이를 말합니다.

  - 다시 말해 모든 경우의 수를 다 체크하여 정답을 찾는 방법을 말합니다.

  - 4개 숫자의 자물쇠🔒를 예로 0~9999까지 10000만의 경우 전부를 확인하여 일치 여부를 확인하는 것 입니다.

  - 그렇기 때문에 무조건 정답을 찾을 수 있습니다.

    <br>

- 모든 경우의 수를 컴퓨터가 수행합니다

  - 문제 해답이 떠오르지 않을 때 컴퓨터의 연산 능력을 믿고 가는 방법입니다.

<br>

## 1. Brute Force의 종류

1. 반복/ 조건문 활용

   <br>

2. 순열 

   - 임의의 수열이 있을 때 그것을 다른 순서로 연산하는 방법

   - n개의 원소 중 r개의 원소를 골라 중복없이 나열

   - 재귀 호출 : 원소를 선택하느냐 마느냐를 결정하며 선택할 갯수를 찾을 때 까지 재귀

     <br>

3. 조합

   - n개의 원소중 r개의 원소를 순서 없이 선택

     cf) 순열 : 순서 O / 조합 : 순서 X

     <br>

4. 멱집합

   - 부분 집합 : 원소 모음인 집합에서 일부or전부 원소를 택해 새로운 집합을 만드는 것을 말합니다.
   - 멱집합: 만들 수 있는 모든 부분집합들의 집합 입니다.

   <br>

   <br>

   <br>

---

## 2. 순열

- 임의의 수열이 있을 때 그것을 다른 순서로 연산하는 방법입니다.

  ![image-20231208134543827](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231208134543827.png)

- n개의 원소 중 r개의 원소를 골라 중복 허용 없이 나열하는 방법입니다.

  - 만들 수 있는 열의 갯수는 아래와 같습니다.

    ![image-20231208103742961](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231208103742961.png)

    ![image-20231208103829363](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231208103829363.png)

  <br>

  <br>

  

### 2.1. 가장 간단한 수열 만들기

- 3개의 원소 중 3개를 골라 수열을 만드는 간단한 코드를 작성해보겠습니다.

  ```java
  public static void perSimple () {
      int first;
      int second;
      int third;
      // 0에서 2사이의 숫자를 차례대로 골라본다.
      for (int i = 0; i < 3; i++){
          // 첫번째 숫자를 골랐음
          first = i;
          // 0에서 2사이의 숫자 중, 아직 고르지 않은 숫자를 골라본다.
          for (int j = 0; j < 3; j++) {
              // 이미 고른 숫자라면 나머지는 실행하지 않는다
              if (first == j) {
                  continue; // coutinue는 가장 가까운 for을 건너 뛴다
              }
              second = j;
              for (int k = 0; k < 3; k++) {
                  if (k == first || k == second) {
                      continue;
                  }
                  third = k;
                  System.out.println(first + " " + second + " " + third);
              }
          }
      }
  }
  ```

- 상기 코드에서 지정된 숫자 3을 n으로 바꾸면 원하는 숫자의 수열을 확인할 수 있습니다.

  - 아래는 10 (n 범위 : 0~9)을 입력하였을 때 출력 결과입니다.

    ![image-20231208110755153](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231208110755153.png)

<br>



- 위의 코드는 골라야 하는 것이 몇개 안될 때, 그리고 골라야 하는 갯수를 미리 알고 있을 때 사용하기 좋습니다.

- 만약 골라야 할 갯수를 알지 못한다면 재귀함수 포함하여 수열을 구현할 수 있습니다.

  ```java
  // 사용성을 위해 실제 메서드를 분리한다. (n과 r만 있어도 실행이 되게끔)
  public static void perRecursive(int n, int r) {
      perRecurHelper(n, r, 0, new boolean[n], new int[r]);
  }
  
  public static void perRecurHelper(int n, int r, int depth, boolean[] used, int[] perm) {
      if (depth == r) {
          System.out.println(Arrays.toString(perm));
      } else {
          //n개의 원소중 하나를 선택하는 for
          for (int i = 0; i < n; i++) {
              // 이미 선택했다면 스킵
              if (used[i]) continue;
  
              // 선택을 할 때 first = i; 의 형태로 작성했던 부분
              perm[depth] = i;
              // 내가 이번에 i를 선택했다는 걸 기록
              used[i] = true;
              // 중첩된 for 대신 재귀 호출
              perRecur(n, r, depth + 1, used, perm);
              // 이 i에서 출발하는 순열을 다 찾으면, 다음 i를 쓰기위해 기록 변경
              used[i] = false;
          }
      }
  }
  ```



<br>

<br>

<br>

----

## 3. 조합

<br>

- n개의 원소중 r개의 원소를 순서 없이 선택하는 것을 말합니다.

  - 순열은 순서가 있고, 조합은 순서가 없습니다.

  ![image-20231208134622489](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231208134622489.png)

- n개의 원소 중 r개의 원소를 골라 중복 허용 없이 고르는 방법입니다.

  - 고르는 경우의 수는 아래와 같습니다.

    ![image-20231208135128962](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231208135128962.png)

<br>

- 5개 중 3개를 선택하는 조합을 간단하게 구현하여 보겠습니다.

  ```java
  public class Combination {
      // 5개 중에서 3개를 선택하는 방법들을 출력하는 메서드 (5C3)
      public static void combSimple(int num) {
          int n = 5;
          // i는 0부터 n - 2까지 반복하고,
          for (int i = 0; i < n - 2; i++) {
              int first;
              int second;
              int third;
              first = i;
              //j는 i+1 부터 n -1까지 반복하고,
              for (int j = first + 1; j < n - 1; j++) {
                  second = j;
                  //k는 j+1부터 n까지 반복한다
                  for (int k = second + 1 ; k < n; k++) {
                      third = k;
                      System.out.println(first + "" + second + "" + third);
                  }
              }
          }
      }
      public static void main(String[] args) {
          combSimple(5);
      }
  }
  ```

  - 첫번째 [i] : 0부터 n-2까지 반복합니다
  - 두번째 [j] : i+1부터 n-1까지 반복합니다.
  - 세번째 [k]: j+2부터 n까지 반복합니다

  <br>

  <br>

  ✨결과

  ![image-20231208141418129](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231208141418129.png)



- 재귀함수로 숫자 범위와 고르는 숫자를 지정할 수 있습니다.

  ```java
  public static void combRecur(int n, int r) {
      combRecurHelper(n, r, 0, 0, new int[r]);
  }
  
  //✨💻 재귀함수 nCr을 구하는 메서드
  // 매개변수 : 몇개(n) 중에서 몇개(r)를 고를지
  // 여태까지 몇개의 원소를 골랐는지를 나타내는 count
  // 이번에 고를지 말지를 판단하는 숫자 next (0~9까지 차례로 커짐)
  // 조합 결과를 담을 배열 comb
  
  
  public static void combRecurHelper(int n, int r, int count, int next, int[] comb) {
      // r개 골라야 하는데 다 골랐다면 comb를 출력한다
      if (count == r) {
          System.out.println(Arrays.toString(comb));
      }
      // 만약 내가 고르려고 고려할 애가 범위를 벗어날려 한다면 함수를 종료한다.
      else if (next == n) {
          return;
      }
      else {
          // 만약 내가 이번에 next를 골랐다
          comb[count] = next;
          // count 번째 원소를 골랐으니, count + 1번째 원소를 고르러 가자
          combRecurHelper(n, r, count + 1, next + 1, comb);
          // count 번째 원소를 고르지 않고 다음 원소를 확인하자
          combRecurHelper(n, r, count, next + 1, comb);
      }
  }
  ```
  
  <br>
  
  <br>
  
  

---

### @ Reference

- https://hongjw1938.tistory.com/78