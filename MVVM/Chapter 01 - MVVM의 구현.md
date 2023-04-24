

목차

---



``` csharp
public class DelegateCommand : ICommand
{
    private readonly Action _action;

    public DelegateCommand(Action action)
    {
        _action = action;
    }

    public void Execute(object parameter)
    {
        _action();
    }

    public bool CanExecute(object parameter)
    {
        return true;
    }

    public event EventHandler CanExecuteChanged;
}
```

---

### Data Binding 이란?

데이터를 xml에서 처리할 수 있도록 도와주는 라이브러리이다. 이를 통해 ViewModel에서 변경된 데이터를 Activity나 Fragment가 아닌 xml에서 바로 처리할 수 있게 된다.

---

### Delegate 란?

<br>

* __Delegate의 정의__

Delegate는 우리말로 대리자 또는 위임자라고도 한다. Delegate는 Type이기 때문에 이 타입을 이용하여 변수(객체, instance)를 생성하고, 그 변수를 이용하면 된다.  

Delegate는 함수(메소드)를 대리하는 역할을 한다.  

> **`public int Function(int a, int b);`**  

위의 함수를 호출하려면, Function(3, 4) 와 같은 형태로 호출한다.  
즉, DelegateA(3, 4)와 같이 사용하게 되면 그것이 바로 Function(3, 4)를 호출한 것과 동일한 동작을 하게 된다. 이러한 방법으로 DelegateA가 Function 함수를 대리하게 되는 것이다.  
<br>

* __Delegate의 선언__

함수와 동일하게 선언하되, return 타입 바로 앞에 delegate 키워드를 붙여준다.  

> **`public delegate int DelFunction(int a, int b);`**  

Delegate는 Type이기에 위와 같은 정의는 특정한 모양의 함수를 대리할 수 있는 Type을 정의한 것이다.

  - return 타입이 int인 것은 delegate가 대리할 수 있는 함수의 리턴 타입이 int임을 정의한다.  
  - 함수의 파라미터가 int a, int b 정수 두 개인 것은 delegate가 대리할 수 있는 함수의 파라미터 타입은 정수 2개여야 함을 의미한다.

정리하자면, 이 delegate는 함수를 대리할 수 있는데 그 대리할 수 있는 함수의 모양은 리턴 타입이 int이고, 파라미터는 정수 2개를 가지고 있는 모양의 함수인 것이다. 그렇지 않은 함수는 이 delegate가 대리할 수 없게 된다.  

---

* __Delegate의 사용__

선언한 delegate를 이용해서 instance를 만들려면 다음과 같이 하면 된다.

> **`DelFunction delFunction;`**  

이제 delFunction은 다음의 함수를 대리할 수 있게 된다.

> **`public int Function(int a, int b)`**

위 함수를 대리자에게 대리시키도록 하면 된다. 한마디로 Function 대신 delFunction을 시켜서 일을 하게 만드는 것이다.

> **`delFunction = new DelFunction(Function);`**  

<br>

ex)
``` csharp
///<summary>
/// MainWindow.xaml에 대한 상호 작용 논리
/// </summary>
public partial class MainWindow : Window
{
    public delegate int DelFunction(int a, int b);

    public MainWindow()
    {
        InitializeComponent();
        
        DelFunction delFunction;
        delFunction = new DelFunction(function);

        Console.WriteLine("호출 결과 : " + delFunction(3, 4));
    }

    public int function(int a, int b)
    {
        return (a + b);
    }
}
```

---

* __Event__

delegate와 Event는 매우 밀접한 관계이다. 이벤트는 이벤트를 발생시키는 주체와, 이 이벤트를 전달받는 수신자로 나누어 생각하는 편이 이해하기 편하다. 다시 말하자면, 특정 누군가가 특정 타이밍에 이벤트라는 것을 만들어서 뿌리게 된다. 어떤 사건이 벌어졌을 때, 이 사건이 발생했음을 다른 누군가에게 알리는 것이다. 

예를 들어, A,B,C,D,E 는 서로 절친이라 나중에 커서 연락을 잘 못하고 지내더라도, 결혼할 때만큼은 꼭 서로에게 연락을 주기로 약속했다. 이후 세월이 흘러 어느날 A가 결혼을 하게 되어 그 약속을 잊지 않고, B,C,D,E 에게 모두 청첩장을 보내주었다. 이때,

`A : 이벤트 발생(송신) 주체`  
`B,C,D,E : 이벤트 수신 주체`  
`청첩장 : 실제 이벤트의 데이터`  
`약속 : 이벤트의 등록`  

와 같이 생각할 수 있다.


---

* __Delegate & Event__

``` csharp
public partial class MainWindow : Window
{
    public class classA // 친구 A
    {
        // delegate 선언
        public delegate void MyEventHandler(object sender, EventArgs e);
        // event 선언
        public event MyEventHandler myEvent;

        // 이벤트 테스트 함수
        public void eventTest()
        {
            // event가 등록 되어있다면 (약속을 했다면)
            if (myEvent != null)
            {
                // 이벤트를 날린다. (청첩장을 보낸다)
                myEvent(this, new EventArgs());
            }
        }
    };

    public MainWindow() // 친구 B
    {
        InitializeComponent();

        classA A = new classA();
        // 이벤트 등록. 이벤트가 발생했을 때 처리할 함수를 위임
        A.myEvent += A_myEvent;

        // 테스트
        A.eventTest();
    }

    // 이벤트가 발생했을 때 처리할 함수 (EventHandler)
    private void A_myEvent(object sender, EventArgs e)
    {
        Console.WriteLine("청첩장이 도착했습니다.");
    }
}
```
