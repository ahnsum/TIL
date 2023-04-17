
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
