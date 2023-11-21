# MarkDown

## 1️⃣개요

John Gruber가 2004년 개발한 마크업 언어(Markup Language)의 일종입니다.

**📌Markdown의 특징**

1. 문법이 쉽고 간결합니다.

2. 관리가 쉽습니다.

3. 별도의 도구 없이 사용 가능합니다.

4. 다양한 플랫폼에서 사용합니다.

   

**✨전문가는 자신이 한 작업을 보여줄 수 있어야 합니다.**

-> 개발자가 자신의 작업을 보여주기 위해 가장 흔히 사용하는 방법입니다.

- 문서의 구조를 표현 하는 언어로 설계도에 가깝습니다.
- **표현의 자동화**를 위한 언어입니다.



## 2️⃣사용하기

- Visual Studio Code 파일 생성

  > 파일명.md

  ![image-20231116143821304](C:\Users\mmm58\AppData\Roaming\Typora\typora-user-images\image-20231116143821304.png)



**☘️ 문단 문법**

```java
# 마크다운 연습
대표 문단의 내용입니다.

※ 글을 두번째 문단로 내리기 위해서는 Enter키를 2번 입력해야 합니다.  
📌 Space 키를 2번 입력해도 줄바꿈이 가능합니다.  
📌 하지만 문단 내 줄바꿈보다는 **Enter키를 이용해서 문단을 바꾸는 것이 깔끔**합니다.


- 제목은 #을 이용해서 표현합니다.
- #이 많을수록 더 낮은 레벨의 제목입니다.
- 다른 말로 더 작은 문단 제목입니다.


# Heading 1
Heading 1 문단의 내용

## Heading 2
Heading 2 문단의 내용

### Heading 3
Heading 3 문단의 내용

#### Heading 4
Heading 4 문단의 내용

##### Heading 5
Heading 5 문단의 내용

###### Heading 6
Heading 6 문단의 내용
    
    
```

​	상기 코드는 아래와 같이 표현됩니다.

> # 마크다운 연습
>
> 대표 문단의 내용입니다.
>
> ※ 글을 두번째 문단로 내리기 위해서는 Enter키를 2번 입력해야 합니다.
> 📌 Space 키를 2번 입력해도 줄바꿈이 가능합니다.
> 📌 하지만 문단 내 줄바꿈보다는 **Enter키를 이용해서 문단을 바꾸는 것이 깔끔**합니다.
>
> - 제목은 #을 이용해서 표현합니다.
> - \#이 많을수록 더 낮은 레벨의 제목입니다.
> - 다른 말로 더 작은 문단 제목입니다.
>
> # Heading 1
>
> Heading 1 문단의 내용
>
> ## Heading 2
>
> Heading 2 문단의 내용
>
> ### Heading 3
>
> Heading 3 문단의 내용
>
> #### Heading 4
>
> Heading 4 문단의 내용
>
> ##### Heading 5
>
> Heading 5 문단의 내용
>
> ###### Heading 6
>
> Heading 6 문단의 내용



**☘️ 강조 문법**

```java
**굵게 표시** 됩니다.
*기울임 표시* 됩니다.
***굵게 + 기울임*** 됩니다.
~~취소선 표시~~ 됩니다. (일부 프로그램에서 동작)
```

​	상기 코드는 아래와 같이 표현됩니다.

> **굵게 표시** 됩니다.
>
> *기울임 표시* 됩니다.
>
> ***굵게 + 기울임*** 됩니다.
>
> ~~취소 표시~~ 됩니다.  (일부 프로그램에서 동작)



**☘️ 목록 문법**

```java
📌목록을 표현할 때는 자동으로 들여쓰기가 됩니다.
- 목록1을 표현합니다.
	- 목록2를 표현합니다.
      - 목록3을 표현합니다.

* 목록1을 표현합니다.
	* 목록2를 표현합니다.
      * 목록3을 표현합니다.

+ 목록1을 표현합니다.
	+ 목록2를 표현합니다.
      + 목록3을 표현합니다.

```

​	상기 코드는 아래와 같이 표현됩니다.

> 📌목록을 표현할 때는 자동으로 들여쓰기가 됩니다.
>
> - 목록1을 표현합니다.
>   - 목록2를 표현합니다.
>     - 목록3을 표현합니다.
>
> * 목록1을 표현합니다.
>   * 목록2를 표현합니다.
>     * 목록3을 표현합니다.
>
> + 목록1을 표현합니다.
>   + 목록2를 표현합니다.
>     + 목록3을 표현합니다.

```java
~~💩섞어 써도 가능하나 권장하지 않습니다.~~

- 목록1을 표현합니다.
  * 목록2를 표현합니다.
    + 목록3을 표현합니다. 
```

​	상기 코드는 아래와 같이 표현됩니다.

> ~~💩섞어 써도 가능하나 권장하지 않습니다.~~
>
> - 목록1을 표현합니다.
>   * 목록2를 표현합니다.
>     + 목록3을 표현합니다. 



```java
1. 숫자 목록1을 표현합니다.
    1. 들여쓰기 4칸을 이용하면
    2. 하위목록 작성이 가능합니다.

2. 숫자 목록2를 표현합니다.
    1. 들여쓰기 4칸을 이용하면
    2. 하위목록 작성이 가능합니다.

3. 숫자 목록3를 표현합니다.
```

​	상기 코드는 아래와 같이 표현됩니다.

> 1. 숫자 목록1을 표현합니다.
>    1. 들여쓰기 4칸을 이용하면
>    2. 하위목록 작성이 가능합니다.
>
> 2. 숫자 목록2를 표현합니다.
>    1. 들여쓰기 4칸을 이용하면
>    2. 하위목록 작성이 가능합니다.
>
> 3. 숫자 목록3를 표현합니다.



**☘️ 코드 문법**

📌문단 내부에 소스코드를 표현하고 싶다면 백틱을 써줍니다.

- 동일 가격 글자로, 색을 바꿔서 소스코드임을 markdown이 알려줍니다.

```

`System.out.println("Hello world");`

```

​	상기 코드는 아래와 같이 표현됩니다.

> `System.out.println("Hello world");`



📌 만약 여러줄의 코드를 표현하고 싶다면 세개를 씁니다.

````
```
public class Main {

 public static void main(){

  System.out.println("Hello world");

 }

}
```
````

​	상기 코드는 아래와 같이 표현됩니다.

> ```
> public class Main {
> 
>  public static void main(){
> 
>   System.out.println("Hello world");
> 
>  }
> 
> }
> ```



📌Github 같은 경우 어떤 언어로 된 코드인지도 작성 가능합니다.

````java
```java
public class Main {
  public static void main(){
    System.out.println("Hello world");
  }
}
```
````

​	상기 코드는 아래와 같이 표현됩니다.

> ```java
> public class Main {
> 
>  public static void main(){
> 
>   System.out.println("Hello world");
> 
>  }
> 
> }
> ```



**☘️ 링크 문법**

📌 꺽쇠(<>)안에 웹페이지 주소를 작성하면 하이퍼링크가 생성됩니다.

```
간단한 하이퍼 링크 생성 : <https://www.naver.com>
문구를 사용한 하이퍼 링크 생성 : [네이버(문구)](https://www.naver.com)
```

​	상기 코드는 아래와 같이 표현됩니다.

> 가장 간단한 링크 만들기 :  <https://www.naver.com>
>
> 문구를 사용한 하이퍼 링크 생성 : [네이버(문구)](https://www.naver.com)



**☘️ 이미지 문법**

📌 대괄호([문구 지정])와 소괄호((경로 지정))를 사용하여 이미지를 첨부할 수 있습니다.  느낌표(!)를 맨 앞에 입력하면 마크다운에 이미지가 바로 표시됩니다.

```
[](image.gif)
[컴퓨터 저장된 이미지(문구)](image.gif)
![컴퓨터 저장된 이미지(문구)](image.gif)
```

​	상기 코드는 아래와 같이 표시 됩니다.

> [](image.gif)
> [컴퓨터 저장된 이미지(문구)](image.gif)
> ![컴퓨터 저장된 이미지(문구)](image.gif)



📌 소괄호에 웹페이지에서 가져온 이미지 주소를 기입하여도 됩니다.

```
[Web image](https://altools.co.kr/_next/static/media/img_feature_alsee_1.da0eae6f.png)
![Web image](https://altools.co.kr/_next/static/media/img_feature_alsee_1.da0eae6f.png)
![](https://altools.co.kr/_next/static/media/img_feature_alsee_1.da0eae6f.png)
```

​	상기 코드는 아래와 같이 표시 됩니다.

> [Web image](https://altools.co.kr/_next/static/media/img_feature_alsee_1.da0eae6f.png)
> ![Web image](https://altools.co.kr/_next/static/media/img_feature_alsee_1.da0eae6f.png)
> ![](https://altools.co.kr/_next/static/media/img_feature_alsee_1.da0eae6f.png)