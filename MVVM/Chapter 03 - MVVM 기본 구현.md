
* __MainViewModel 기본형__

``` csharp
namespace MyMVVM.ViewModel
{
    class MainViewModel : INotifyPropertyChanged
    {
        public event PropertyChangedEventHandler = PropertyChanged;

        protected void OnPropertyChanged(string propertyName)
        {
            PropertyChangedEventHandler handler = PropertyChanged;

            if (handler != null)
            {
                handler(this, new PropertyChangedEventArgs(propertyName));
            }
        }
    }
}
```

<br>

* __Model 기본형__

``` csharp
namespace MyMVVM.Model
{
    class MainModel : INotifyPropertyChanged
    {
        public event PropertyChangedEventHandler = PropertyChanged;

        protected void OnPropertyChanged(string propertyName)
        {
            PropertyChangedEventHandler handler = PropertyChanged;

            if(handler != null)
            {
                handler(this, new PropertyChangedEventArgs(propertyName));
            }
        }
    }
}
```

<br>

* __Command 기본형__

``` csharp
namespace MyMVVM.Command
{
    class DelegateCommand : ICommand
    {
        Action<object> _execute;
        Func<object, bool> _canExecute;

        public DelegateCommand(Action<object> execute, Func<object, bool> canExecute)
        {
            _execute = execute; // Action으로 버튼에 바인딩된 Command가 실제로 실행할 함수
            _canExecute = canExecute; // Action이 수행되기 전에 필요한 조건을 검사하는 메소드
        }

        public event EventHandler CanExecuteChanged
        {
            add { CommandManager.RequerySuggested += value; }
            remove { CommandManager.RequerySuggested -= value; }
        }

        public bool CanExecute(object parameter)
        {
            return _canExecute == null ? true : _canExecute(parameter);
        }

        public void Execute(object parameter)
        {
            _execute.Invoke(parameter);
        }
    }
}
```

<br>

* View와 ViewModel 연결

``` csharp
namespace MyMVVM
{
    public partial class MainWindow : Window
    {
        public MainWindow
        {
            InitializeComponent();
            this.DataContext = new MainViewModel(); // View와 ViewModel을 연결
        }
    }
}
```

