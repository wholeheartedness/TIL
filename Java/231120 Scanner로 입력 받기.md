# Scanner로 입력 받기

## 1. Scanner

### 1.1 Scanner 사용 개요

- 사용자의 입력을 받을 수 있습니다.

- 사용자의 입력을 변수를 지정하여 저장할 수 있습니다.

  ```java
  Scanner scanner = new Scanner(System.in);
  String scannedLine = scanner.nextLine();
  System.out.println(scannedLine);
  ```

- 입력 받을 변수의 자료형을 결정할 수 있습니다.

  ```java
  scanner.next<자료형>(); 
  ```

  - 문자형: nextLine()
  - 정수형: nextInt(), nextLong(), nextShort(), nextByte()
  - 실수형: nextFloat(), nextDouble()
  - 논리형: nextBoolean()
    - 논리형은 true/false를 입력으로 받습니다. (0/1❌)

  

### 1.2 Scanner 사용 주의 사항

- 입력은 한 줄 단위가 아닌, 만족하는 수치를 자동으로 받습니다.

  ```java
  int scannedInt = scanner.nextInt();
  long scannedLong = scanner.nextLong();
  System.out.println(scannedInt);
  System.out.println(scannedLong);
  
  float scannedFloat = scanner.nextFloat();
  double scannedDouble = scanner.nextDouble();
  System.out.println(scannedFloat);
  System.out.println(scannedDouble);
  ```

  >  아래와 같이 출력 됩니다
  >
  > ![image-20231120144828007](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231120144828007.png)



- 상기 사항을 주의해야 합니다. `123 45 정수 입력!` 을 입력했을 때 아래 예시코드의 출력 값은?

  ```java
  Scanner scanner = new Scanner(System.in);
  scanner.nextInt();
  String scannedLine = scanner.nextLine();
  System.out.println(scannedLine); 
  ```

  >  아래와 같이 출력 됩니다.
  >
  > ![image-20231120145624988](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231120145624988.png)
  >
  > '123'은 scanner.nextInt()로 입력을 받았고
  >
  > '45 정수 입력 '은 scanner.nextLine()으로 입력을 받았습니다.
  >
  > 사용자의 입력을 주의하여 scanner를 사용해야 합니다.
  >
  > ![image-20231120150622872](https://raw.githubusercontent.com/wholeheartedness/image_repo/main/img/image-20231120150622872.png)