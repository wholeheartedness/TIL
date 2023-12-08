# Sort

<br>

## 1. Bubble Sort(버블 정렬)

- 인접한 두 데이터를 비교하며 자리를 교환하는 방식입니다.

- [0] - [1] / [1] - [2] / [2] - [3] / ..... [n-1] - [n] 의 방식으로 자료를 비교하며 교환합니다.

- 1회전 수행 후 가장 큰 자료가 뒤로 이동합니다.

- 2회전 수행 시 가장 큰 자료를 제외하고 비교하여 2번째로 큰 자료를 [n-1]에 위치시킵니다.

- 같은 방식으로 정렬이 끝날 때 까지 수행합니다.

  ![img](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/bubble-sort.png)

  <center> &lt; Bubble Sorting &gt; </center>

<br>

![File:Bubble sort animation.gif](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/Bubble_sort_animation.gif)

<center> &lt; random list using bubble sort &gt; </center>

<br>

<br>

### 1.1. 소스코드

```java
import java.util.Arrays;

public class Sorting {
    public static void bubbleSort(int[] array) {
        int length = array.length;
        // 2️⃣length -1 번 반복한다
        for (int i = 0; i < length - 1; i++) {
            // 1️⃣끝으로 옮기는 작업을
            for (int j = 0; j < length - 1; j++) {
                // j와 j+1을 비교한다.
                if (array[j] > array[j + 1]) {
                    // 더 크면 교환
                    // 💡temp라는 임시 공간을 두고 array j 값을 저장 하고 옮긴 후 temp를 다시 할당한다.
                    int temp = array[j];
                    array[j] = array[j + 1];
                    array[j + 1] = temp;
                }
            }
        }
    }

    public static void main(String[] args) {
        int[] array = {31, 13, 16, 14, 46, 18};
        bubbleSort(array);
        System.out.println(Arrays.toString(array));
    }
}

```



**✨결과**

- 아래와 같이 출력 됩니다.

  ![image-20231205103816091](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231205103816091.png)

<br>

<br>

### 1.2. 시간복잡도

- 1회전 : N-1번의 비교가 일어납니다.

- 2회전 : N-2번의 비교가 일어납니다.

- 3회전 : N-3번의 비교가 일어납니다.

- ...

- N-1 회전 : 1번의 비교가 일어납니다.

- 등차수열로 정리하면 Big-O notation으로 ON^2 입니다.

  ![image-20231205144101554](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231205144101554.png)

### @ Reference

- https://gmlwjd9405.github.io/2018/05/06/algorithm-bubble-sort.html
- https://ko.wikipedia.org/wiki/%EB%B2%84%EB%B8%94_%EC%A0%95%EB%A0%AC

<br>

<br>

<br>

---

<br>

<br>

## 2. Selection Sort (선택 정렬)

- 주어진 데이터 중 제일 작은 숫자를 골라 앞으로 정렬하는 방식입니다.

- Bubble Sort와 비교군이 다른 방식입니다.

- Bubble Sort보다 비교 정렬 연산 과정이 적습니다.

- Bubble Sort와 정렬 결과는 같습니다.

  ![img](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/selection-sort.png)

<center> &lt; Selection Sorting &gt;</center>

<br>

<center> <img src = "https://upload.wikimedia.org/wikipedia/commons/9/94/Selection-Sort-Animation.gif"></center>

<center> &lt; Selection sort animation &gt;</center>

<br>

<br>

### 2.1. 소스 코드

```java
public class Sorting {
    public static void selectionSort(int[] array) {
        int length = array.length;
        int min = array[0];

        // array의 원소 중 최솟값이 어디 있는지를 찾는다
        for (int i = 0; i < length - 1; i++) {
            // 현재 정렬되지 않은 제일 앞쪽 원소는 i
            int minIndex = i;
            for (int j = i+1; j < length; j++) {
                if (array[minIndex] > array[j]) {
                    minIndex = j;
                }
            }
            // 제일 작은 원소와 제일 앞의 원소를 교환한다. 
            // (temp에 저장 후 작은 수 앞으로 옮긴 후 재할당)
            int temp = array[minIndex];
            array[minIndex] = array[i];
            array[i] = temp;
            System.out.println("round" + i + ":" + Arrays.toString(array));
        }
    }

    public static void main(String[] args) {
        int[] array = {31, 13, 16, 14, 46, 18};
        //bubbleSort(array);
        selectionSort(array);
        System.out.println(Arrays.toString(array));
    }
}
```

<br>

**✨ 결과**

- 아래와 같이 출력 됩니다.

  ![image-20231205113121272](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231205113121272.png)

<br>

<br>

### 2.2. 시간복잡도

- 1회전 : N-1번의 비교가 일어납니다.
- 2회전 : N-2번의 비교가 일어납니다.
- 3회전 : N-3번의 비교가 일어납니다.
- ...
- N-1 회전 : 1번의 비교가 일어납니다.
- 등차수열로 정리하면 Big-O notation으로 ON^2 입니다.

![image-20231205164436839](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231205164436839.png)



- 시간 복잡도는 Bubble Sort와 동일하나
- Bubble Sort는 가장 큰 수가 가장 앞에 있으면 할당이 n-1번이 일어나나
- Selection Sort는 가장 작은 수가 앞에 있으면 할당이 1번 일어나기 때문에
- 실제 데이터가 교환되는 횟수가 적습니다

<br>

<br>

### @ Reference

- https://gmlwjd9405.github.io/2018/05/06/algorithm-selection-sort.html
- https://en.wikipedia.org/wiki/Selection_sort

<br>

<br>

<br>

---

<br>

<br>

## 3. Counting Sort(계수 정렬)

- 각 데이터가 몇개 존재하는지 정리한 뒤 그 정보를 활용하여 정리하는 방식 입니다.

- 데이터들끼리 서료 비교하지 않고 정렬합니다.

  ![image-20231205144458619](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231205144458619.png)

<center> &lt; Counting Sorting &gt;</center>

<br>

- `a (input Array)` : Array를 받습니다.

<br>

- `c (Counting Array)`: Array의 데이터들을 카운트하는 배열을 생성합니다.

  - a에 속한 각 데이터가 몇개 존재하는지 c에 오름차순으로 카운트합니다

  - c에 데이터가 생성 됐습니다.

  <br>

- `c'(Counting Array's 누적합)` : c의 데이터를 누적합 합니다.

<br>

- `b(Output Araray)` : Array와 같은 length의 배열 b를 생성합니다.

  - c'는 a[n]의 데이터가 어디까지 존재하는지 에 대한 정보입니다.

  - b에 c' 데이터를 가지고 값을 채워 넣습니다.

    <br>

💡참고 animation : [Counting Sort][https://www.cs.miami.edu/home/burt/learning/Csc517.091/workbook/countingsort.html]

<br>

### 3.1. 소스코드

```java
public static void countingSort(int[] array) {
    // 원래는 max를 찾아야 되는데
    // 이번만큼은 47임을 알고있다 가정한다.
    int[] counts = new int[47];
    // 모든 array 데이터를 순회하면서 각 counts[data]++;
    for (int data : array) {
        counts[data]++;
    }

    // counts 배열을 각 데이터가 마지막에 나오는 위치가 담기게 조정
    for (int i = 0; i < 46; i++) {
        // 다음칸에 지금칸의 데이터를 담아준다.
        counts[i + 1] += counts[i];
    }
    // counts 중간점검
    System.out.println(Arrays.toString(counts));

    // 결과를 담을 배열 만들기 (output)
    int[] output = new int[array.length];
    // 뒤에서부터 순회하며 output 배열 채우기.
    for (int i = array.length - 1; i >= 0; i--) {
        // 현재 원소의 마지막 위치를 조정
        counts[array[i]]--;
        // 현재 데이터의 다음 위치 정보를 회수
        int position = counts[array[i]];
        // 새로운 배열의 position에 데이터 넣기
        output[position] = array[i];
    }

    // 원본에 새로운 데이터 적용하기
    for (int i = 0; i < array.length; i++) {
        array[i] = output[i];
    }
```

<br>

✨ 결과

![image-20231205140141780](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231205140141780.png)

<br>

<br>

### 3.2. 시간복잡도

- 데이터 갯수(N)와 데이터 값의 범위(최댓값 K), 동시에 영향을 받습니다.

  - N 영향 1) counts 배열을 만들기 위해 전체 자료를 살펴봐야 합니다.

  - K 영향 1) counts 배열을 누적합 하는 과정에서  counts 배열을 전체 살펴봐야 합니다.

  - N 영향 2) 다시 전체 자료를 순회하며 결과 배열을 만듭니다.

    <br>

- `c (Counting Array)`를 만드는 단계에서 N번의 계산이 이루어 집니다

- `c'(Counting Array's 누적합)`를 만드는 과정에서 K+1번의 계산이 이루어 집니다

- `b(Output Araray)`를만드는 단계에서 N번의 계산이 이루어 집니다.

  <br>

- `2N + K + 1`으로, Big-O notation으로는 O(n+k) 입니다.

  ![image-20231205135241013](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231205135241013.png)

- 데이터의 범위가 (데이터의 갯수)^2 를 넘어가면
- O(N^2) 인 알고리즘보다 효율이 좋지 못합니다.

<br>

<br>

### @ Reference

- https://opendatastructures.org/ods-java/11_2_Counting_Sort_Radix_So.html

<br>

<br>

<br>

---

<br>

<br>

## 4. Binary Search (이진 탐색)

- 이미 정렬된 데이터 리스트에서 검색 범위를 절반으로 줄여가며 검색 값을 찾는 방법 입니다.

  - 검색이 반복될 때 마다 검색 범위가 절반으로 줄기 때문에 속도가 빠릅니다. 🏃

  ![image-20231205141045937](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231205141045937.png)

<center> &lt; Binary Searching &gt;</center>

<br>

<br>

### 4.3. 소스 코드

```java
public static int binarySearch(int[] array, int target) {
    // 🪄1) 검색 대상 경계선을 세운다. : 배열의 시작과 끝
    // 시작과 끝 인덱스를 저장한다.
    int leftIndex = 0;
    int rightIndex = array.length - 1;

    // 🪄2)중간 지점을 설정한다 
    // 시작부터 끝까지 절반 길이를 왼쪽 끝에서 출발해서 도달한다.
    int midIndex = (rightIndex - leftIndex) / 2 + leftIndex;
    midIndex = (rightIndex + leftIndex) / 2;

    // 🪄4) 찾을 때 까지 반복한다 
    // left가 커지면 탐색 실패
    while (leftIndex <= rightIndex) {
        // 🪄3) target을 찾는다
        // 3-1. mid에 target이 있을 경우
        if (array[midIndex] == target) {
            return midIndex; 
            //탐색 성공 시 : midIndex를 return 하면서 함수 종료
        }
        // 3-2. mid가 target보다 작을 경우 
        // : target이 mid보다 오른쪽이다
        else if (array[midIndex] < target) {
            leftIndex = midIndex + 1;
        }
        // 3-3. mid가 target보다 클 경우 
        // : target이 mid보다 왼쪽이다
        else {
            rightIndex = midIndex - 1;
        }
    } 
    return -1; 
    //탐색 실패 시 : -1을 반환하면서 함수 종료
}
```



<br>

<br>

### @ Reference

- https://medium.com/@imanshu822/binary-search-and-its-powerful-applications-39ae7d7bca69

- https://en.wikipedia.org/wiki/Binary_search_algorithm

<br>

<br>

<br>