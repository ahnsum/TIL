
마크다운(MarkDown) 문법 정리
--------------------------


 마크다운(markdown)은 일반 텍스트 기반의 경량 마크업 언어이다. 일반 텍스트로 서식이 있는 문서를 작성하는 데 사용되며, 일반 마크업 언어에 비해 문법이 쉽고 간단한 것이 특징이다.

---

<br/>

 #### 0. 태그 종류

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

#### 1.1. 제목(Header)
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

#### 1.2. 인용문(BlockQuote)
* ```>``` 기호
* HTML의 ```<blockquote>```

     중첩 가능
     인용 안에 마크다운 문법 사용 가능


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

#### 1.3. 강조(Emphasis)
* HTML의 ```<bold>```

        This is **Bold**
        This is __Bold__

This is **Bold**
This is __Bold__
    <br/>

* HTML의 ```<i>```

        This is *Italic*
        This is _Italic_

This is *Italic*
This is _Italic_
    <br/>

* HTML의 ```<b> 와 <i>```


<br/>

---

<br/>

#### 1.4. 목록(List)
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

---

<br/>

#### 1.5. 코드

* 들여쓰기 (한줄 띄우기)

        This is a normal paragraph:

            This is a code block.

        end code block.
---

This is a normal paragraph:

    This is a code block.

end code block.

---




<br/>

---

<br/>

#### 형광펜

```css
<span style='background-color:#FFF5B1'>노란형광펜</span>
<span style='background-color:#D7D3D1'>회색형광펜</span>
<span style='background-color:#BBDEFB'>파랑형광펜</span>
<span style='background-color:#F6C0BE'>빨강형광펜</span>
<span style='background-color:#C0F2A1'>초록형광펜</span>
<span style='background-color:#D1C0ED'>보라형광펜</span>
<span style='background-color:#FFCFB0'>주황형광펜</span>
```
