# Git & Github

## 1️⃣Git 개요

### 📌형상 관리 (버전 관리) 도구

- 리눅스를 개발하고 있던 Linus Torvalds가 만든 버전 관리 프로그램

  (이메일로 버전을 주고 받는데에 불편함을 느껴서 만듦)

  - version : 개발 단계와 순서를 번호로 표시한 것
  - 관리 : 시설이나 물건의 유지, 개량

​			![image-20231117164520033](2.git_github.assets/image-20231117164520033.png)

![image-20231117164445176](../SEiZE_THE_DAY/image/markdown/image-20231117164445176.png)

- 이전 버전 대비 달라진 점인 '변경점'을 따로 생성합니다.

![image-20231117092850033](C:\Users\mmm58\AppData\Roaming\Typora\typora-user-images\image-20231117092850033.png)

- 최종 상태와 변경점만 남깁니다.

  ➡️어떤 내용의 변경이 있었는지 확인 가능

  ➡️누가, 언제, 왜 와 같은 이력 정보 확인 가능

  ➡️최초의 원본은 변경점들을 다시 확인하면 알 수 있음



### 📌분산 버전 관리 도구

- 이전(SVN): 큰(중앙) 서버에 전체 프로젝트를 관리

  -  개발자가 서버에서 필요한 부분만 가져와 일부분 수정 후 다시 서버로 보내는 방식
  - ex. 위키피디아

- 현재(Git): 큰(중앙) 서버에 원본을 저장

  - 참여 개발자는 동일한 전체 버전을 저장 (변경점만 기록하므로 용량에 부담이 없음)
  - 자신이 변경한 내용을 서버로 전송

  ☘️ 서버 불안정에 대해서 비교적 안정적으로 프로젝트 관리가 가능합니다.

  

## 2️⃣Git과 Github

- Git : 프로젝트 관리를 위한 프로그램
- Github : Git으로 관리하는 프로젝트의 저장소를 마련해주는 서비스



## 3️⃣Git 사용하기

### 📌  Git 설치하기(Windows)

1. 홈페이지(https://git-scm.com/)에 접속합니다.![image-20231117094806023](C:\Users\mmm58\AppData\Roaming\Typora\typora-user-images\image-20231117094806023.png)

2. 사용자 OS에 맞는 버전을 다운로드 해줍니다.![image-20231117094852358](C:\Users\mmm58\AppData\Roaming\Typora\typora-user-images\image-20231117094852358.png)
3. 운영 체제에 맞는 버전을 다운로드 합니다![image-20231117094921879](C:\Users\mmm58\AppData\Roaming\Typora\typora-user-images\image-20231117094921879.png)
4. 설치를 진행합니다.![image-20231117100306607](../../AppData/Roaming/Typora/typora-user-images/image-20231117100306607.png)![image-20231117100313673](../../AppData/Roaming/Typora/typora-user-images/image-20231117100313673.png)

![image-20231117100322140](../../AppData/Roaming/Typora/typora-user-images/image-20231117100322140.png)

![image-20231117100329010](../../AppData/Roaming/Typora/typora-user-images/image-20231117100329010.png)

![image-20231117100337800](../../AppData/Roaming/Typora/typora-user-images/image-20231117100337800.png)

![image-20231117100354950](../../AppData/Roaming/Typora/typora-user-images/image-20231117100354950.png)

![image-20231117100422031](../../AppData/Roaming/Typora/typora-user-images/image-20231117100422031.png)

![image-20231117100432620](../../AppData/Roaming/Typora/typora-user-images/image-20231117100432620.png)

![image-20231117100445685](../../AppData/Roaming/Typora/typora-user-images/image-20231117100445685.png)

![image-20231117100453045](../../AppData/Roaming/Typora/typora-user-images/image-20231117100453045.png)

- 엔터키를 어떻게 설정할 것인지 

![image-20231117100514143](../../AppData/Roaming/Typora/typora-user-images/image-20231117100514143.png)

![image-20231117100521194](../../AppData/Roaming/Typora/typora-user-images/image-20231117100521194.png)

![image-20231117100528248](../../AppData/Roaming/Typora/typora-user-images/image-20231117100528248.png)

![image-20231117100534828](../../AppData/Roaming/Typora/typora-user-images/image-20231117100534828.png)

![image-20231117100544653](../../AppData/Roaming/Typora/typora-user-images/image-20231117100544653.png)

![image-20231117100552108](../../AppData/Roaming/Typora/typora-user-images/image-20231117100552108.png)

![image-20231117101445869](../../AppData/Roaming/Typora/typora-user-images/image-20231117101445869.png)

- 언제, 무엇을, 어떻게, 왜 : Git이 자동으로 작업
- 누가 : 사용자가 설정

1. Git 커맨드 창에 아래의 코드를 작성하여 email을 설정합니다.

```
$ git config --global user.email "Git에서 사용할 이메일"
```

2. Git 커맨드 창에 아래의 코드를 작성하여 name을 설정합니다.

```
$ git config --global user.email "Git에서 사용할 닉네임"
```

3. Git 커맨드 창에 아래의 코드를 작성하여 설정한 email과 name을 확인합니다.

```
$ git config user.email
$ git config user.name
```

![image-20231117102233022](../../AppData/Roaming/Typora/typora-user-images/image-20231117102233022.png)



### 📌Git 사용하기

1. 폴더를 생성하고 해당 폴더에서 "Open Git Bash here"을 사용해 Git bash를 엽니다.

![image-20231117103125160](../../AppData/Roaming/Typora/typora-user-images/image-20231117103125160.png)

2. VS Code에서 같은 폴더를 엽니다.

3. Git Bash에서 아래의 코드를 작성합니다.

   ```
   git init
   git status
   ```

   ![image-20231117103319408](../../AppData/Roaming/Typora/typora-user-images/image-20231117103319408.png)

4. 이제 해당 폴더는 git이 관리해주게 되는데, 확인하기 위해 해당 폴더에 Test 페이지를 만들어 봅니다.

   (저는 README.md를 만들었습니다.)

   ![image-20231117105357297](../../AppData/Roaming/Typora/typora-user-images/image-20231117105357297.png)

5. git bash에 아래 코드를 작성합니다.

```
git status
```

​	![image-20231117104755805](../../AppData/Roaming/Typora/typora-user-images/image-20231117104755805.png)

6. 아래 코드를 작성합니다. (README.md 에 자신이 만든 파일명을 기록합니다.)

   - git add: 해당 파일을 작업 이력으로 기록할 준비

   ```
   git add README.md
   ```

   -  git commit : add된 파일들을 바탕으로 새로운 변경사항(작업)을 기록

   ```
   git commit -m "add README.md"
   ```

   ![image-20231117105213633](../../AppData/Roaming/Typora/typora-user-images/image-20231117105213633.png)

   (명령어를 입력하고 git status를 통해 진행 상태를 확인했습니다.)

   

   ![image-20231117105048942](../../AppData/Roaming/Typora/typora-user-images/image-20231117105048942.png)

   - 추가 되지 않아야 할 파일을 구분하기 위하여 add를 선택적으로 합니다.

   - .gitignore에 추가하고 싶지 않은 파일 명을 입력하면 추적하지 않습니다.

     ![image-20231117111426905](../../AppData/Roaming/Typora/typora-user-images/image-20231117111426905.png)

     ![image-20231117111443784](../../AppData/Roaming/Typora/typora-user-images/image-20231117111443784.png)



### 📌Git 사용하기 - 버전 되돌리기

- 대상 파일을 "현재 버전(마지막으로 커밋된 상태)"로 되돌릴 수 있습니다.

```
git restore README.md
```

- 대상 파일을 add한 후에는 아래의 명령어로 이전 상태로 되돌리 수 있습니다.

```
git restore --staged README.md
git restore README.md
```

- 없애고 싶은 commit 바로 다음 commit 시리얼을 넣으면 앞전에 했던 commit은  사라지고 파일 상태는 그대로 둘 수 있습니다.

  (💩웬만하면 사용하지 않습니다)

```
git reset 시리얼번호
```

## 5️⃣Github연동하기

1. git hash에서 아래 명령어를 입력합니다.

   ```
   ssh-keygen
   ```

   - 아래 화면이 나올때 까지 enter키를 눌러줍니다

     ![image-20231117132321076](../../AppData/Roaming/Typora/typora-user-images/image-20231117132321076.png)

2. 아래 명령어를 입력합니다.

   ```
   $ cat .ssh/id_rsa.pub
   ```

   

   ![image-20231117132425494](../../AppData/Roaming/Typora/typora-user-images/image-20231117132425494.png)

   - SSH Key가 발급되었습니다. 

3. Github에 로그인하여 오른쪽 상단 프로필 사진을 클릭-Settings에 들어갑니다.

4. 왼쪽 사이드 메뉴의 SSH and GPG eys 메뉴- SSH Keys-New SSH key에 들어간 후 발급받은 SSH 키를 입력합니다.

   ![image-20231117132834857](../../AppData/Roaming/Typora/typora-user-images/image-20231117132834857.png)

   ![image-20231117132820143](../../AppData/Roaming/Typora/typora-user-images/image-20231117132820143.png)

5. 패스워드를 입력하면 적용됩니다.

   ![image-20231117132936985](../../AppData/Roaming/Typora/typora-user-images/image-20231117132936985.png)

6. 새로운 repository를 생성하고 SSH 버튼을 눌러 주소를 복사합니다.

   ![image-20231117142300960](../../AppData/Roaming/Typora/typora-user-images/image-20231117142300960.png)

   ![image-20231117133909605](../../AppData/Roaming/Typora/typora-user-images/image-20231117133909605.png)

7.  git을 연동할 폴더에서 git bash 터미널을 열고 아래 명령어를 입력합니다.

   ```
   git clone git@github.com:아이디/git-demo.git
   ```

   ![image-20231117134144890](../../AppData/Roaming/Typora/typora-user-images/image-20231117134144890.png)

   - continue connecting 문구가 뜨면 yes를 입력합니다.
   - warning : You appear to have cloned an empty repository 문구를 확인하면 완료입니다.

   ![image-20231117134304893](../../AppData/Roaming/Typora/typora-user-images/image-20231117134304893.png)

   - 해당 폴더에 repository 명(git-demo)의  새로운 폴더가 생성된 것을 확인할 수 있습니다.

​					이제 github와 새로운 repository를 사용할 준비가 끝났습니다.



### 📌Github에 올리기

1. 해당 폴더에 README.md 파일을 생하고 git에서 add 및 commit을 해줍니다.

   ![image-20231117135605768](../../AppData/Roaming/Typora/typora-user-images/image-20231117135605768.png)

   ![image-20231117135445126](../../AppData/Roaming/Typora/typora-user-images/image-20231117135445126.png)

2. 아래 명령어를 입력합니다.

   ```
   git push
   ```

   ![image-20231117135513613](../../AppData/Roaming/Typora/typora-user-images/image-20231117135513613.png)

3. Github에서 해당 repository를 들어가면 README.md 파일이 업로드 된 것을 확인할 수 있습니다.

   ![image-20231117135548177](../../AppData/Roaming/Typora/typora-user-images/image-20231117135548177.png)

- 한번 더 테스트 해보았습니다.

  ![image-20231117141324995](../../AppData/Roaming/Typora/typora-user-images/image-20231117141324995.png)

  ![image-20231117141342890](../../AppData/Roaming/Typora/typora-user-images/image-20231117141342890.png)

  잘 반영됨을 확인할 수 있습니다.

  ![image-20231117141403224](../../AppData/Roaming/Typora/typora-user-images/image-20231117141403224.png)



### 📌Github에서 내려받기

1. github에서 연필모양의 아이콘을 눌러 내용을 추가 후 commit changes를 클릭합니다.

![image-20231117141622429](../../AppData/Roaming/Typora/typora-user-images/image-20231117141622429.png)

![image-20231117141915511](../../AppData/Roaming/Typora/typora-user-images/image-20231117141915511.png)

2. commit  메세지를 입력하고 최종적으로 Commit Changes를 클릭합니다.

![image-20231117141557934](../../AppData/Roaming/Typora/typora-user-images/image-20231117141557934.png)

3. 아래 명령어를 터미널에 입력합니다

   ```
   git pull
   ```

   ![image-20231117141809576](../../AppData/Roaming/Typora/typora-user-images/image-20231117141809576.png)

4. 컴퓨터 내 파일에 정상적으로 반영됩니다.

   ![image-20231117141834757](../../AppData/Roaming/Typora/typora-user-images/image-20231117141834757.png)



### 📌기존 폴더를 Github에 업로드 하기

1. github 홈에서 repository를 새로 생성합니다

   ![image-20231117142845765](../../AppData/Roaming/Typora/typora-user-images/image-20231117142845765.png)

2. repository name은 폴더명으로 지정하고 생성된 repository의 SSH를 복사합니다.

   (💡repository name은 자유롭게 작성해도 되나 명확하게 알기 위해 폴더명으로 지정했습니다.)

   ![image-20231117142932017](../../AppData/Roaming/Typora/typora-user-images/image-20231117142932017.png)

   ![image-20231117142948221](../../AppData/Roaming/Typora/typora-user-images/image-20231117142948221.png)

3. 해당 폴더에서 git bash 터미널을 열고 아래 명령어를 입력합니다.

   ```
   git remote add origin git@github.com:<아이디>/git-practice.git
   git push --set-upstream origin main
   ```

   ![image-20231117143530951](../../AppData/Roaming/Typora/typora-user-images/image-20231117143530951.png)

   ![image-20231117143552027](../../AppData/Roaming/Typora/typora-user-images/image-20231117143552027.png)

   - push 시 아래와 같은 오류가 발생한다면 git status 명령어를 입력하여 브랜치 명을 확인하고 origin 이후 브랜치 명을 바꿔주세요.

     (ex. git push --set-upstream origin 현재브랜치명)

     ![image-20231117143910098](../../AppData/Roaming/Typora/typora-user-images/image-20231117143910098.png)

     error: failed to push some refs to 'github.com:wholeheartedness/3.git-practice.git'

     ![image-20231117144006822](../../AppData/Roaming/Typora/typora-user-images/image-20231117144006822.png)

   - 아래의 명령어로 브랜치 명을 main으로 변경할 수 있습니다.

     ```
     git config --global init.defaultBranch main
     ```

4. 기존 폴더가 github에 정상적으로 반영되었습니다.

   ![image-20231117143619309](../../AppData/Roaming/Typora/typora-user-images/image-20231117143619309.png)

#### 💡컴퓨터 commit과 서버 commit이 겹쳤다면?

![image-20231117144654717](../../AppData/Roaming/Typora/typora-user-images/image-20231117144654717.png)

![image-20231117144715584](../../AppData/Roaming/Typora/typora-user-images/image-20231117144715584.png)

- git push를 하면 오류가 발생합니다

​	![image-20231117144902269](../../AppData/Roaming/Typora/typora-user-images/image-20231117144902269.png)

- git pull을 해도 오류가 발생합니다.

​				![image-20231117145003922](../../AppData/Roaming/Typora/typora-user-images/image-20231117145003922.png)

- 파일 확인하면 아래와 같이 표시됩니다.

  ![image-20231117145041287](../../AppData/Roaming/Typora/typora-user-images/image-20231117145041287.png)

- 해당 부분을 확인하고 작업자가 올바른 쪽으로 수정하여 다시 commit합니다.

  ![image-20231117145227296](../../AppData/Roaming/Typora/typora-user-images/image-20231117145227296.png)

  ![image-20231117145242039](../../AppData/Roaming/Typora/typora-user-images/image-20231117145242039.png)

- 컴퓨터와 서버 파일에서 충돌이 해결되었습니다.

  ![image-20231117145310344](../../AppData/Roaming/Typora/typora-user-images/image-20231117145310344.png)

📌Git Readme에 링크 넣기

![image-20231117152635654](../../AppData/Roaming/Typora/typora-user-images/image-20231117152635654.png)