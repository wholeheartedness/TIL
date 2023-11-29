# Collection Framework

## 1. 컬렉션 프레임워크

**✨컬렉션**

- 여러 객체(데이터)를 모아놓은 것 입니다.

  <br>

**✨프레임 워크**

- 표준화, 정형화된 체계적인 프로그래밍 방식 입니다.

  <br>

**✨컬렉션 프레임 워크**

- 컬렉션을 다루기 위한 표준화된 프로그래밍 방식입니다.

  - java.util 패키지에 포함됩니다

  ![image-20231129095043420](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231129095043420.png)

  ![image-20231129095122134](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231129095122134.png)

  - List : 순서가 있는 저장 공간

  - Set : 집합적인 저장 공간

  - Map : 키와 같으므로 데이터 핸들

    <br>

**✨컬렉션 클래스**

- 컬렉션을 쉽고 편리하게 다루기 위해 Java에서 먼저 만들어준 데이터 정리용 클래스 입니다.
- 다수의 데이터를 저장할 수 있는 클래스 입니다
  - Vetor
  - ArrayList
  - Hashset
  - ...
- 구현 클래스를 통해 실제 자료 구조를 달리 고를 수 있습니다.

<br>

<br>

<br>

---

## 2. List

- List는 순서가 있는 데이터를 인터페이스 입니다.

  - 데이터의 중복이 허용됩니다.

  - 원소를 일렬로 세워 추가/제거/조회 등을 위해 많이 활용됩니다.

    <br>

- 📌ArrayList : 동적으로 배열의 크기를 바꿔가며 활용합니다

  - 임의의 위치에서 원소를 가져오기 좋습니다.

- 📌LinkedList : 연결 리스트 형태로 데이터를 관리합니다.

  - 원소를 추가/제거 하는데 유리합니다.

<br>

- List를 생성하겠습니다.

  ```java
  List<String> f4Names = new ArrayList<>();
  f4Names.add("구준표");
  f4Names.add("윤지후");
  f4Names.add("소이정");
  f4Names.add("송우빈");
  System.out.println(f4Names.get(0)); //구준표
  System.out.println(f4Names.get(1)); //윤지후
  System.out.println(f4Names.get(2)); //소이정
  System.out.println(f4Names.get(5)); //소이정
  ```

  - String 배열을 선언하는 것 과는 차이가 있습니다.

  - String 배열은 배열의 순서를 알아야 합니다.

    ```java
    String[] f4Array = new String[4];
    f4Array[0] = "구준표";
    f4Array[1] = "윤지후";
    f4Array[2] = "소이정";
    f4Array[3] = "송우빈";
    ```

<br>

- **get() 메서드**로 ArrayList의 원소를 확인할 수 있습니다.

  - 작성한 인덱스의 원소를 반환합니다

  ```java
  System.out.println(f4Names.get(0)); //구준표
  System.out.println(f4Names.get(1)); //윤지후
  System.out.println(f4Names.get(2)); //소이정
  System.out.println(f4Names.get(5)); //error
  ```

  <br>

- **add() 메서드**로 ArrayList의 원소를 추가 할 수 있습니다.

  - 성공하면 true를 반환합니다.

  ```java
  f4Names.add(2, "금잔디");
  System.out.println(f4Names); //[구준표, 윤지후, 금잔디, 소이정, 송우빈]
  f4Names.add("성덕선");
  System.out.println(f4Names); //[구준표, 윤지후, 금잔디, 소이정, 송우빈, 성덕선]
  ```

  <br>

- **indexOf()** 메서드로 데이터의 위치를 찾을 수 있습니다.

  - 데이터가 있으면 그 인덱스를, 데이터가 없으면 -1을 반환합니다.

  ```java
  System.out.println("금잔디 ist at: " + f4Names.indexOf("금잔디")); //금잔디 ist at: 2
  System.out.println("성보라 ist at: " + f4Names.indexOf("성보라")); //성보라 ist at: -1
  ```

  <br>

- **remove()** 메서드로 데이터를 삭제할 수 있습니다.

  - 인덱스에 있는 원소를 제거하고 반환합니다.
  - 뒤에 남은 원소들을 앞으로 당겨옵니다.

  ```java
  //순서를 기준으로 (value)
  System.out.println(f4Names.remove(3)); //소이정
  System.out.println(f4Names); 
  //[구준표, 윤지후, 금잔디, 송우빈, 성덕선]
  
  //값을 기준으로 (boolean) 
  System.out.println(f4Names.remove("성덕선")); //true
  System.out.println(f4Names.remove("성덕선")); 
  //false
  System.out.println(f4Names); 
  //[구준표, 윤지후, 금잔디, 송우빈]
  ```

- **size()** 메서드로 데이터의 개수를 셀 수 있습니다.

  ```java
  System.out.println(f4Names); //[구준표, 윤지후, 금잔디, 소이정, 송우빈, 성덕선]
  System.out.println(f4Names.size()); //6
  ```

  <br>

- ❌ 원시타입은 사용하지 못합니다.

  ``` List<int> intList = new ArrayList<>();```

- ⭕ 그래서 Wrapper로 사용합니다.

  ``````
  List<Integer> intList = new ArrayList<>();
  intList.add(10);
  intList.add(20);
  intList.add(30);
  intList.add(40);
  System.out.println(intList); //[10, 20, 30, 40]
  System.out.println(intList.remove(2)); //30
  System.out.println(intList.remove(Integer.valueOf(50))); //false
  ``````

<br>

- ✨✨ ⭕매개변수로 전달할 때는 기능을 중요시하는 interface를 기준으로 매개변수를 선언합니다. 

  ```java
  public static int sum(List<Integer> intList) {
      return 0;
  }
  ```

- ❌구현을 중시하는 방식으로 요구를 하면 기능적 측면의 차이가 없는 클래스는 하나도 사용하지 못합니다.

  ```java
  public static int sum(ArrayList<Integer> intList) {
      return 0;
  }
  ```

<br>

<br>

<br>

---

## 3. Set

- Set은 순서를 유지하지않는 데이터의 집합입니다.

  - 데이터의 중복을 허용하지 않습니다.

  <br>

- 📌HashSet : 객체의  hashCode를 활용하여 객체를 구분하는 집합입니다.

  - HashSet을 사용하기 위해서는 hashCode를 꼭 구현해야 합니다.
  - hashCode() : 각 객체의 주소값을 반환하여 생성한 객체의 고유한 정수값 입니다.
    - 별개의 개체에 대해 고유한 정수를 반환합니다. (일종의 ID 입니다.)

<br>

- Set을 선언해보겠습니다.

  ```java
  Set<String> dayRutin = new HashSet<>();
  ```

- **add()** 메서드로 데이터를 추가합니다.

  - 단, **중복 데이터는 추가가 안됩니다**.
  - 또한 **데이터의 순서를 보장하지 않습니다**.

  ```java
  Set<String> dayRutinSet = new HashSet<>();
  dayRutinSet.add("기상");
  dayRutinSet.add("수업듣기");
  dayRutinSet.add("알고리즘풀기");
  dayRutinSet.add("학습회고");
  dayRutinSet.add("아르바이트");
  dayRutinSet.add("아르바이트");
  System.out.println(dayRutinSet); //[학습회고, 기상, 아르바이트, 알고리즘풀기, 수업듣기]
  ```

  - 다른 컬렉션인 weekendRutinList의 원소를 추가해보도록 하겠습니다.

    ```java
    List<String> weekendRutinList = new ArrayList<>();
    weekendRutinList.add("기상");
    weekendRutinList.add("부산가기");
    weekendRutinList.add("데이트하기");
    weekendRutinList.add("술먹기");
    weekendRutinList.add("유튜브보기");
    System.out.println(weekendRutinList); //[기상, 부산가기, 데이트하기, 술먹기, 유튜브보기]
    ```

  - **set이 없는 원소들을 선별하여 추가**합니다.

  - 하나라도 **추가하는데 성공하면 true를 반환**, 모두 중복되어 추가할 것이 없으면 false를 반환합니다.

    ```java
    System.out.println(dayRutinSet.addAll(weekendRutinList)); //true
    System.out.println(dayRutinSet); 
    // [학습회고, 기상, 아르바이트, 알고리즘풀기, 술먹기, 데이트하기, 유튜브보기, 수업듣기, 부산가기]
    ```

- Set이 어떻게 중복을 처리 할까요?

- 아래의 문제로 알아보겠습니다.

  ```
  비둘기집 원리
  비둘기가 들어갈 수 있는 집이 10개인데
  비둘기가 11마리라면
  누군가는 한방에 두마리 이상이 들어간다.
  ```

  - Pigeon 클래스를 생성합니다.

    ```java
    public class Pigeon {
        private int age;
    
        public Pigeon(int age) {
            this.age = age;
        }
    }
    ```

  - Main 메서드에서 20마리의 비둘기를 Pigeon 클래스의 객체로 생성합니다. 비둘기는 0~9까지의 나이를 가집니다.

    ```java
    List<Pigeon> listHoles = new ArrayList<>();
    Set<Pigeon> setHoles = new HashSet<>();
    
    //20마리의 비둘기 만들기
    for (int i = 0; i < 20; i++) {
        Pigeon pigeon = new Pigeon(i % 10); //0,1,2,....,9,0,1,2,...,9 : 총 20마리
        listHoles.add(pigeon);
        setHoles.add(pigeon);
    }
    ```

  - HashCode를 생성하지 않으면 각 개체로써 나이를 가지므로 모두 20마리가 생성됩니다.

    ```java
    System.out.println("리스트의 비둘기 마리 :" + listHoles.size()); // 20
    System.out.println("집합의 비둘기 마리 :" + setHoles.size()); // 20
    ```

- **removeAll() 메서드**로 어떠한 배에 포함된 데이터들을 삭제할 수 있습니다.

  - 다른 ArrayList인 favoriteRutin을 생성해보겠습니다.

    ```java
    List<String> favoriteRutin = new ArrayList<>();
    favoriteRutin.add("샌드위치 먹기");
    favoriteRutin.add("책읽기");
    favoriteRutin.add("영화보기");
    favoriteRutin.add("술먹기");
    favoriteRutin.add("유튜브보기");
    ```

  - removeAll()로 삭제합니다.

    ```java
    //아이템 제거하기
    System.out.println(dayRutinSet.removeAll(favoriteRutin));
    System.out.println(dayRutinSet); //[학습회고, 기상, 아르바이트, 알고리즘풀기, 데이트하기, 수업듣기, 부산가기]
    ```

- **clear() 메서드**로 배열을 삭제할 수 있습니다.

  ```java
  dayRutinSet.clear();
  System.out.println(dayRutinSet); //[]
  ```

<br>

<br>

<br>

---

## 4. Iterable & Collection

- Collections와 Framework의 기초가 되는 인터페이스로 Iterable과 Collection이 있습니다.

  - List와 Set은 이 두가지 인터페이스를 상속받는 인터페이스 입니다.

  <br>

- 📌Iterable(반복가능한) : 해당 객체를 통해 원소를 하나씩 살펴 볼 수 있습니다. 

  - Iterable : 책입니다. 글의 목록입니다.

  - Iterator : 독자입니다. 글을 읽습니다.

    - hasNext() : boolean의 반환형을 가지고 있습니다.

    - next() : 다음으로 볼 글 호출합니다.

      <br>

- 📌Collection(컬렉션) : Iterable을 상속받는 인터페이스로 List 와 Set이 실제로 정의된 인터페이스 입니다.

  - 컬렉션 인터페이스를 구현하는 클래스는  꼭 아래 항목을 생성해야 합니다

    - 아무것도 없는 기본 생성자
    - 다른 Collection을 받아 그 모든 원소를 가지는 생성자

  - Set을 사용하는 와중에 List로 변환하고 싶다면 ArrayList 등의 클래스를 만들면서 Set을 전달하면 됩니다.

  - 아래는 생성 예시입니다.

    ```java
    List<String> listWithDuplicates = new ArrayList<>();
    listWithDuplicates.add("Java");
    listWithDuplicates.add("Java");
    listWithDuplicates.add("Java");
    listWithDuplicates.add("Java");
    listWithDuplicates.add("Java");
    Set<String> setNoDuplicates = new HashSet<>(listWithDuplicates);
    System.out.println(setNoDuplicates);
    ```

<br>

- Iterable , Collection , List , Set 모두 순회가 가능합니다.

  <br>

- dayRutinList 라는 ArrayList를 생성해보겠습니다.

  ```java
  List<String> dayRutinList = new ArrayList<>();
  dayRutinList.add("기상");
  dayRutinList.add("수업듣기");
  dayRutinList.add("알고리즘풀기");
  dayRutinList.add("학습회고");
  dayRutinList.add("아르바이트");
  ```

  - foreach로 모든 원소들을 읽어냅니다.

    ```java
    for (String rutin : dayRutinList) {
        System.out.println(rutin);
    }
    /*
    기상
    수업듣기
    알고리즘풀기
    학습회고
    아르바이트
    */
    ```

  - 중간에 데이터 하나를 삭제해보겠습니다.

    ```java
    for (String rutin : dayRutinList) {
        System.out.println(rutin);
        dayRutinList.remove("아르바이트");
    }
    ```

  - 에러가 발생합니다.

  - 순회 중에 제거 동작이 발생하여 foreach 동작에 오류가 발생했기 때문입니다.

    ![image-20231129133710380](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231129133710380.png)

<br>

- Iterator 객체를 사용하여 아래와 같이 표현할 수도 있습니다.

  ```java
  Iterator<String> iter = dayRutinList.iterator();
  while (iter.hasNext()) { // 실제 데이터를 가지고 옵니다.
      String rutin = iter.next();
      System.out.println(rutin);
  }
  ```

  - iter.remove() 메소드를 사용하여 중간에 데이터 하나를 삭제해보겠습니다.

  - 순회 중 제거를 해도 정상적으로 동작합니다.

    ```java
    if("아르바이트".equals(rutin)){
        iter.remove();
    }
    System.out.println(dayRutinList);
    //[기상, 수업듣기, 알고리즘풀기, 학습회고]
    ```

    <br>

<br>

<br>

---

## 5. Map 

- Key와 Value의 쌍으로 이루어진 인터페이스 입니다.

- Value를 저장하고 이 Value를 찾기 위한 용도의 Key를 저장합니다

- 이 후 Key를 활용하여 데이터를 회수 할 수 있습니다.

  - Key는 중복이 안됩니다
  - Value는 중복이 됩니다
  - Map은 순서가 없습니다
  - 데이터 등장 횟수를 세는 알고리즘 등으로 활용할 수 있습니다.

- Collection 인터페이스를 구현하지는 않습니다.

- Key와 Value를 입력 받아 정의합니다.

  ```java
  Map<String, String> contactBook = new HashMap<>();
  ```

  <br>

- 아래의 전화번호부 예시 코드로 알아보겠습니다.

- **put("key", "value") 메서드**로 데이터를 입력할 수 있습니다.

  - key에 value을 할당 후 null을 반환하고 (✅null Check)
  - 이미 지정한 key라면 이미 할당 된 value을 반환합니다.

  ```java
  Map<String, String> contactBook = new HashMap<>();
  //Map에 연락처 저장
  contactBook.put("구준표", "010-1111-1111");
  contactBook.put("윤지후", "010-2222-2222");
  contactBook.put("송이정", "010-3333-3333");
  System.out.println(contactBook.put("송우빈", "010-4444-4444")); //null
  System.out.println(contactBook.put("송우빈", "010-5555-5555")); //010-4444-4444
  ```

  - 할당된 key에 value를 할당하면 덮어씌웁니다.

    ```java
    contactBook.put("구준표", "010-1111-2222");
    System.out.println(contactBook.get("구준표")); //010-1111-2222
    ```

    <br>

- **get("key") 메서드**로 값을 회수할 수 있습니다.

  - 할당되지 않은 key는 null을 반환합니다. (✅null Check)

  ```java
  System.out.println(contactBook.get("구준표"));
  ```

  <br>

- **keySet()**으로 **key만으로 구성된 Set**을 **순회** 할 수 있습니다.

  - foreach로 반복합니다

  ```java
  for (String key : contactBook.keySet()) {
      System.out.println(key); //key만 출력
  /*
  송우빈
  구준표
  윤지후
  송이정
  */
      System.out.println(contactBook.get(key)); //value만 출력
  /*
  010-5555-5555
  010-1111-2222
  010-2222-2222
  010-3333-3333
  */
  }
  ```

- **entrySet()**으로 **key-value 쌍으로 구성된 Set**을 **순회** 할 수 있습니다.

  - foreach로 반복합니다

  ```java
  for (Map.Entry<String, String> entry : contactBook.entrySet()) {
      System.out.println(entry); //key와 value 출력
  /*
  송우빈=010-5555-5555
  구준표=010-1111-2222
  윤지후=010-2222-2222
  송이정=010-3333-3333
  */
      
      System.out.println(entry.getKey()); //key만 출력
  /*
  송우빈
  구준표
  윤지후
  송이정
  */
      
      System.out.println(entry.getValue()); //value만 출력
  }
  /*
  010-5555-5555
  010-1111-2222
  010-2222-2222
  010-3333-3333
  */
  ```

<br>

- 또다른 예제코드로 class4의 점수를 가져오는 class4Score Map을 생성해보겠습니다.

  ```java
  Map<String, Integer> class4Score = new HashMap<>();
  class4Score.put("Korean", 10);
  class4Score.put("Math", 20);
  class4Score.put("English", 15);
  class4Score.put("Science", 30);
  System.out.println(class4Score); //{English=15, Science=30, Korean=10, Math=20}
  ```

- 만약, 데이터를 넣어야 하는 상황에 새로운 과목이 생기면 2가지 방법으로 구현할 수 있습니다.

- class4Score.get("score") == null 를 활용한 예시입니다.

  ```java
  if (class4Score.get(newSubject) == null) {
      class4Score.put(newSubject, 40);
  } else {
      int before = class4Score.get(newSubject);
      class4Score.put(newSubject, before + 40);
  }
  ```

- putIfAbsent를 활용한 예시입니다.

  ```java
  Integer before2 = class4Score.putIfAbsent(newSubject, 40);
  if (before2 != null) {
      class4Score.put(newSubject, before2 + 40);
  }
  System.out.println(class4Score); //{Social=80, English=15, Science=30, Korean=10, Math=20}
  ```

- value로써 Collection(Set, List)를 쓰고 싶다면 아래와 같이 구현할 수 있습니다.

  ```java
  //Value로써 Collection(Set,List)를 쓰고 싶다면?
  Map<String, List<String>> class4Student = new HashMap<>();
  class4Student.put("Korean", new ArrayList<>());
  List<String> KoreanStudents = class4Student.get("Korean");
  KoreanStudents.add("구준표");
  KoreanStudents.add("금잔디");
  KoreanStudents.add("윤지후");
  KoreanStudents.add("구준표");
  System.out.println(class4Student); //{Korean=[구준표, 금잔디, 윤지후, 구준표]}
  ```