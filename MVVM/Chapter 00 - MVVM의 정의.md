
MVVM 패턴 정리
-------------

MVVM 패턴은 Model, View, ViewModel의 줄임말로, 하나의 소프트웨어를 최대한 기능적으로 작은 단위로 나누어 테스트가 쉽고, 큰 프로젝트도 상대적으로 관리하기 좋은 구조입니다.

---

<br>

### 0. MVVM

* **View**
    - 사용자가 보는 화면(UI)을 구성 (XAML) 
``` 
- 모든 입력(Input)이 전달  
- 자신이 이용할 ViewModel을 선택해 바인딩하여 업데이트를 받음  
- ViewModel을 관찰하고 있다가 상태 변화가 전달되면 화면을 갱신
```
* **ViewModel**
    - View, UI의 실제 동작에 관련된 부분 작성
```
- View와 Model 사이의 매개체 역할
- 입력에 해당하는 Presentation Logic을 처리하여 View에 데이터 전달  
- View를 따로 참조하지 않기 때문에 독립적이며, MVP와 다르게 ViewModel과 View는 1:n 관계  
- View를 나타내기 위한 Model이자, View의 Presentation Logic을 처리
- 모든 View와 관련된 비즈니스 로직이 들어가게 되며 데이터를 잘 가공해서 View에서 나타내기 쉬운 Model로 바꾸는 역할
- View가 데이터 바인딩(Data Binding)할 수 있는 속성과 명령으로 구성
```
* **Model**
    - ViewModel에서 사용할 데이터 정의
```
- MVC의 Model과 동일한 역할
- 상태 및 데이터가 변경되면 해당하는 ViewModel을 이용하는 View가 자동으로 업데이트
- 다양한 데이터 소스로부터 필요한 데이터 준비
- ViewModel에서 데이터를 가져갈 수 있게 데이터를 준비하고 그에 대한 이벤트를 보냄
```

<br/>

---

<br/>

* 기본적인 MVVM 구조

    <details>
    <summary><u>MVVM 구조</u></summary>
    <div markdown="1">

    ![image](https://velog.velcdn.com/images%2Fjojo_devstory%2Fpost%2F5d3e1aa5-28bc-45d3-964f-36e60e4e9088%2F%EC%BA%A1%EC%B2%98.PNG)

    </div>
    </details>



<br/>

---

<br/>


## <u> MVC, MVP 와 MVVM </u>

<br/>

* ### MVC

    `MVC(Model-View-Controller) 패턴` 은 웹 어플리케이션에서 가장 많이 쓰이는 디자인 패턴 중 하나이다.

    <br/>

    <details>
    <summary><u>MVC 구조</u></summary>
    <div markdown="1">

    ![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fccvfx0%2FbtrEcv1XMTU%2Ft3OMVhzMmZae9KvQpjXae1%2Fimg.png)


    </div>
    </details>

    <br/>

    - __Model__ : 
            -비즈니스 로직을 나타내고 클래스의 집합으로 특징  
            -이 부분은 데이터가 바뀌고 조작되는지에 대한 비즈니스 규칙을 디자인하는데 동작  
    - __View__ : 
            -UI 컴포넌트를 나타냄  
            -View는 Controller가 폼 형태로 되돌려준 결과를 보여줌  
            -Model은 UI에 View로 변환될 수 있음  
    - __Controller__ : 
            -들어오는 요청을 처리하기 위해 Controller는 아주 반응적임  
            -Model에서 View로 가는 과정을 통해, Controller는 사용자의 데이터를 가져옴  
            -Model과 View 사이에 Controller는 협력자 역할을 함  


<br/>

---

<br/>


* ### MVP

    `MVP(Model-View-Presenter) 패턴` 에서는 페이지 조절과 전시가 뷰에 의해서 이루어진다.

    <br/>

    <details>
    <summary><u>MVP 구조</u></summary>
    <div markdown="1">

    ![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fq7nXu%2FbtrD3yS2pNY%2FxdQRAbVqOBKJHAaQcp7wuK%2Fimg.png)


    </div>
    </details>

    <br/>

    - __Model__ : 
            -비즈니스 로직을 나타내고 클래스의 집합으로 특징  
            -이 부분은 데이터가 바뀌고 조작되는지에 대한 비즈니스 규칙을 디자인하는데 동작  
    - __View__ : 
            -UI 컴포넌트를 나타냄  
            -View는 Controller가 폼 형태로 되돌려준 결과를 보여줌  
            -Model은 UI에 View로 변환될 수 있음  
    - __Presenter__ : 
            -View를 대신하여 모든 UI이벤트를 알려주기 위해, Presenter는 온전한 책임을 짐  
            -View는 사용자로부터 입력을 제공하고 데이터는 Model의 도움으로 필터되며, 결과는 View로 전달  
            -Presenter와 View는 완전히 다른 것들이지만, 서로 통신하기 위해 인터페이스를 사용  



<br/>

---

<br/>


* ### MVVM

    `MVVM(Model-View-ViewModel) 패턴` 에서는 View와 ViewModel 사이의 양방향 데이터 바인딩을 볼 수 있다.

    <br/>

    <details>
    <summary><u>MVVM 구조</u></summary>
    <div markdown="1">

    ![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FI0Ia7%2FbtrEaN93m03%2FQvgBPWN6BlfR7dcRQ9g2a0%2Fimg.jpg)


    </div>
    </details>

    <br/>

    - __Model__ : 
            -비즈니스 로직을 나타내고 클래스의 집합으로 특징  
            -이 부분은 데이터가 바뀌고 조작되는지에 대한 비즈니스 규칙을 디자인하는데 동작  
    - __View__ : 
            -UI 컴포넌트를 나타냄  
            -View는 Controller가 폼 형태로 되돌려준 결과를 보여줌  
            -Model은 UI에 View로 변환될 수 있음  
    - __ViewModel__ : 
            -ViewModel의 책임 중 하나는 메서드와 함수들을 나타내는 것  
            -Model을 작동하기 위한 명령을 나타내고, View의 상태를 유지시키고 View의 이벤트를 활성화 시킴  


<br/>

---

<br/>

* MVVM의 장점

    - Model과 View 사이, ViewModel과 View 사이의 의존성이 없음
    - 기능별로 모듈화되어 있어 역할 분리를 할 수 있고 유닛 테스트가 더 쉬워짐
    - MVP 패턴에서처럼 테스트를 위한 가상 뷰를 만들 필요없이, 테스트할 때 모델이 변경되는 시점에 옵저버블(관찰) 변수가 제대로 설정됐는지 확인
    - 데이터바인딩 라이브러리를 이용함으로써 UI 코드는 네이티브 코드에 관여하지 않아도 됨
    - View가 데이터를 실시간으로 관찰
      + 직접 View를 바꿔주는 번거로움을 없애고 데이터와 불일치할 확률 최소화
    - 생명주기로부터 안전하여 메모리 누수를 방지
      + 화면전환과 같이 액티비티가 파괴된 후 재구성 되어도 ViewModel이 데이터를 홀드하고 있기 때문에 영향을 받지 않음
      + View가 활성화 되어 있을 경우에만 작동하기 때문에 불필요한 메모리 사용 최소화  


---
<br>


### MVVM 패턴이란 

Activity에 기능을 붙이다보면 Activity가 무거워지거나 혹은 종속성이 너무 강해 테스트가 힘들고 유지보수가 어려워진다. 이에 MVVM은 `View` - `ViewModel` - `Model`을 이용해 각각의 역할을 분리하여 가독성과 재사용성을 높인 디자인 패턴이다.  
<br>

### MVC와 MVVM의 차이점

기존 MVC(Model - View - Controller) 구조에서는 Activity가 Controller의 역할을 했으며, View와 연결되어 사용자와 상호작용도 하고, Model과 연결되어 데이터도 처리했다. 즉, View와 Model 사이에서 중재자 역할을 했다.  <br>

MVVM에서는 View에서 ViewModel로, ViewModel에서 Model로 작업을 처리하며, View에서 Model을 직접 참조하지 않는다. 대신 View에서 ViewModel을 관찰하며 데이터의 변경 사항을 감지한다.  

<details>
<summary><u>MVC와 MVVM의 차이점</u></summary>
<div markdown="1">

![image](https://blog.yena.io/assets/post-img19/190316-mvc-mvvm.png)

</div>
</details>

<br>

__MVC__ 에서는 Controller가 사용자의 클릭 액션을 확인하고, Model에 데이터를 갱신하도록 요청하고, View에도 화면을 업데이트 하라고 요청해야한다. 코딩을 하다가 무언가 빠뜨리면 때로는 DB만 갱신되고 화면은 갱신되지 않는 경우도 나타난다.  <br>

__MVVM__ 에서도 View가 사용자의 클릭 액션을 확인하지만, View에서 곧바로 DB에 접근하지 않는다. 말 그대로 'View'이기 때문에 UI를 갱신하는 역할에 충실하다. 대신 ViewModel을 참조하고, ViewModel에서는 다시 Model에서 잘 정리된 데이터를 참조한다. 또, View는 ViewModel을 __관찰(Observe)__ 한다. DB에 새로운 아이템을 추가한 후에 화면을 업데이트 하라고 직접 명령하지 않아도 된다. View에서는 이미 ViewModel을 관찰하고 있기 때문에 데이터의 변화를 알아차리고 자동으로 화면을 갱신한다. 
<br>

### MVVM의 장점

__1. View가 데이터를 실시간으로 관찰!__  
LiveData, 즉 Observable 패턴을 이용하기 때문에 데이터베이스를 관찰하고 자동으로 UI를 갱신한다. 직접 View를 바꾸어주는 번거로움도 없으며 데이터와 불일치할 확률이 줄어든다.  

__2. 생명주기로부터 안전! 메모리 릭 방지!__  
ViewModel을 통해 데이터를 참조하기 때문에 액티비티/프래그먼트의 생명주기를 따르지 않는다. 화면전환과 같이 액티비티가 파괴된 후 재구성 되어도 ViewModel이 데이터를 홀드하고 있기 때문에 영향을 받지 않는다. 또한 View가 활성화되어있을 경우에만 작동하기 때문에 불필요한 메모리 사용을 줄일 수 있다.  

__3. 역할 분리! 모듈화!__  
UI, 비즈니스 로직, 데이터베이스가 기능별로 모듈화 되어있어서 역할별로 정리가 깔끔하다. 유닛 테스트가 한결 용이해진다.  

모듈화가 잘 되어있다면 다음과 같은 상황에서 편하게 코딩이 가능할 것 같다.  
* 내장 DB를 통째로 바꾸고 싶다고 할 때, View나 다른 코드에 깊게 종속돼있지 않기 때문에 DB만 쓱 교체해주면 된다.  

* ViewModel과 View가 1:n 연결이 가능하기 때문에, ViewModel에 하나의 메소드를 구현해 놓으면 A 액티비티든 B 액티비티든 여러 뷰에서 호출해 재사용하기 편리하다.  

단, 예상되는 단점이라면 MVVM 패턴에선 기존에 비해 추가로 만들어주어야 하는 클래스도 많고, 이들을 서로 코딩하여 연결해주어야 한다. 이 과정이 복잡해지면 기존의 프로젝트에 적용하기는 시간적, 인적 자원이 많이 필요할 것이다.

_https://blog.yena.io/studynote/2019/03/16/Android-MVVM-AAC-1.html_

---

