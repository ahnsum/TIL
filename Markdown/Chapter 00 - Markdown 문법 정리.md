
마크다운(MarkDown) 문법 정리
--------------------------

 마크다운(markdown)은 일반 텍스트 기반의 경량 마크업 언어이다. 일반 텍스트로 서식이 있는 문서를 작성하는 데 사용되며, 일반 마크업 언어에 비해 문법이 쉽고 간단한 것이 특징이다.

---

<br/>

 ### 0. 태그 종류

        제목 : # , =====
        인용 : >
        강조 : * , _
        링크 : [텍스트](주소 "설명")
        이미지 : ![텍스트](이미지 주소 "설명")
        리스트 : 1 , * , - , +
        코드표시 : <code>코드</code> , 한줄 띄우고 스페이스 4칸 , ```코드```
        줄바꿈 : 엔터 2번 , 강제 줄바꿈은 문장 끝에 스페이스 2칸
        가로선 : ----- , ***** , +++++
    

<br/>

---

<br/>

### 1.1. 제목(Header)
* 큰 제목 : 문서 제목

        This is an H1
        ============
    <br/>

* 작은 제목 : 문서 부제목

        This is an H2
        -------------
    <br/> 

* 태그(기호) #

        # 제목1      : HTML의 <h1> 태그
        ## 제목2     : HTML의 <h2> 태그
        ### 제목3    : HTML의 <h3> 태그
        #### 제목4   : HTML의 <h4> 태그
        ##### 제목5  : HTML의 <h5> 태그
        ###### 제목6 : HTML의 <h6> 태그

# 제목1
## 제목2
### 제목3
#### 제목4
##### 제목5
###### 제목6


<br/>

---

<br/>

### 1.2. 인용문(BlockQuote)
* `>` 기호 (3개)
* HTML의 `<blockquote>`

     중첩 가능
     인용 안에 마크다운 문법 사용 가능
     <br>


        > ### This is a first blockquote.
        >> **This is a second blockquote.**
        >>> _This is a third blockquote._
        >>
        >> This is a second blockquote.
        
    <br/>

> ### This is a first blockquote.
>> **This is a second blockquote.**
>>> _This is a third blockquote._
>>
>> This is a second blockquote.

<br/>

---

<br/>

### 1.3. 텍스트
* 강조 (`**` / `__`)  
    -HTML의 `<bold>`  

        This is **Bold**
        This is __Bold__

This is **Bold**  
This is __Bold__
<br/>

* 기울임 (`*` / `_`)  
    -HTML의 `<i>`  

        This is *Italic*
        This is _Italic_

This is *Italic*  
This is _Italic_
<br/>

* 밑줄 (`<u>`)  

        <u>This is Underline</u>

<u>This is Underline</u>
<br/>

* 취소선 (`~~`)  

        ~~This is Canceled~~

~~This is Canceled~~
<br/>

* 글씨색 (`<span>`)

        <span style="color:hotpink">This is Hotpink</span>

<span style="color:hotpink">This is HotPink</span>

* 형광펜 (`==` / `<mark>`)

        ==Highlighter==
        <mark>Highlighter</mark>


==Highlighter==  
<mark>Highlighter</mark>

<br/>


---

<br/>

### 1.4. 목록(List)
* 순서 있는 목록(번호) - 내림차순 정의

        1. 첫번째
        2. 두번째
        3. 세번째

1. 첫번째
2. 두번째
3. 세번째

    <br/>

* 순서 없는 목록(글머리 기호 : *, +, -)

        * 빨강
          * 녹색
            * 파랑
        + 빨강
          + 녹색
            + 파랑
        - 빨강
          - 녹색
            - 파랑

* 빨강
    * 녹색
        * 파랑
+ 빨강
    + 녹색
        + 파랑
- 빨강
    - 녹색
        - 파랑


<br/>

* 체크 리스트

```
    - [ ] 체크 안됨
    - [x] 체크 됨
```

- [ ] 체크 안됨
- [x] 체크 됨

---

<br/>

### 1.5. 코드

* 인라인 코드

        This is `Inline code`

This is `Inline code`
<br/>

* 들여쓰기 (한줄 띄우기)

        This is a normal paragraph:

            This is a code block.

        end code block.


This is a normal paragraph:

    This is a code block.

end code block.


<br/>



* 코드 블럭

        ```c++
        #inclue <iostream>
        using namespace std;

        int main()
        {
            cout << "Hello World!" << endl;
        }
        ```

```c++
#inclue <iostream>
using namespace std;

int main()
{
    cout << "Hello World!" << endl;
}
```
<br/>

---

<br/>


### 1.6. 줄바꿈

* 문장 뒤에 `SpaceBar` 2번 + `Enter`

        Hello.  
        This is Markdown.


Hello.  
This is Markdown.

<br/>

* `<br>` HTML 태그

        Hello. <br> This is Markdown.


Hello. <br> This is Markdown.

<br/>

---

<br/>

### 1.7. 링크

* 링크만 있는 inline 링크 <u>`<링크주소>`</u>

        <https://wwww.google.com>

<https://wwww.google.com>
<br/>

* 설명이 있는 inline 링크 <u>`[링크설명](링크주소)`</u>

        [구글 홈페이지](https://wwww.google.com)

[구글 홈페이지](https://wwww.google.com)
<br/>


* 동일 파일 내에서의 문단(Header) 이동 링크 <u>`[설명어](문단의 주소)`</u>
    1. 헤더 <u>`제목 문자열`</u>을 복사하고 <u>`(문단의 주소)`</u>에 붙여넣기
    2. 특수 문자 제거
    3. 공백을 `-`로 변경
    4. 대문자는 소문자로 변경

    ```
       [태그 종류](###-0.-태그-종류)
    ```

[태그 종류](###-0.-태그-종류)
<br/>

* 이미지 링크 <u>`![image](이미지 주소)`</u>  
    -로컬 파일 경로도 가능  
    -그림 자체에 링크 걸기 가능  

        ![image](이미지 주소)
        ![image](이미지 주소)(이동하려는 링크 주소)


<br/>



---

<br/>

### 1.8. 테이블

* `|`와 `-`(3개 이상)의 조합으로 테이블 생성

    * 정렬
      - 왼쪽 정렬 `|:--|`
      - 오른쪽 정렬 `|--:|`
      - 가운데 정렬 `|:--:|`

    ```
    |**제목**|평점|감상평|
    |:---:|---:|---|
    |짱구는 못말려|⭐⭐⭐⭐⭐|perfect|
    ```  

|**제목**|평점|감상평|
|:---:|---:|---|
|짱구는 못말려|⭐⭐⭐⭐⭐|perfect|

<br/>

---

<br/>


### 1.9. 토글 리스트 (접기/펼치기)

* HTML의 `details` 태그 사용
* <u>`div markdown="1"`</u> 은 html 사이에 markdown 인식하기 위한 코드

        <details>
        <summary>여기를 눌러주세요</summary>
        <div markdown="1">

        ♬ 숨겨진 내용 ♬

        </div>
        </details>


<details>
<summary>여기를 눌러주세요</summary>
<div markdown="1">

 ♬ 숨겨진 내용 ♬

</div>
</details>

<br/>

---

<br/>

### 1.10. 버튼

* 링크 부분 `#` 은 페이지 맨 위로 이동

        <a href="#" class="btn--success">Success Button</a>    

<a href="#" class="btn--success">Success Button</a>


<br/>

---

<br/>


### 형광펜
<br>

<span style='background-color:#FFF5B1'>노란형광펜</span>  
<span style='background-color:#D7D3D1'>회색형광펜</span>  
<span style='background-color:#BBDEFB'>파랑형광펜</span>  
<span style='background-color:#F6C0BE'>빨강형광펜</span>  
<span style='background-color:#C0F2A1'>초록형광펜</span>  
<span style='background-color:#D1C0ED'>보라형광펜</span>  
<span style='background-color:#FFCFB0'>주황형광펜</span>  


<br/>

---

<br/>


### 
