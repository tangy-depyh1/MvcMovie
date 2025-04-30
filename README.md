Editor: Vasynin Sergey ISdo-22
Выбрать "Создать проект" → "Веб-приложение ASP.NET Core (MVC)".
Дать проекту имя (например, MvcMovie), выбрать папку и версию .NET.
Нажать "Создать" – проект готов.
Нажать Ctrl+F5 (без отладки) или F5 (с отладкой).
появится готовый шаблон сайта с базовой структурой (главная страница, меню).




В Обозревателе решений (VS/VS Code) кликнуть ПКМ на Контроллеры → Добавить → Контроллер → MVC - пустой, назвать HelloWorldController.cs.
Заменить код контроллера:
csharp
public class HelloWorldController : Controller  
{  
    public string Index() => "Default action";  
    public string Welcome(string name, int numTimes = 1) => $"Hello {name}, Num: {numTimes}";  
}  
Запустить (CTRL+F5) и проверить:
/HelloWorld → вызов Index().
/HelloWorld/Welcome?name=Test&numTimes=5 → вывод приветствия.
Параметры маршрута (например, /Welcome/3?name=Test) обрабатываются через {id?} в Program.cs.