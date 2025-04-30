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





Изменение контроллера:
В HelloWorldController метод Index() теперь возвращает View() вместо строки, что означает использование Razor-представления для генерации HTML.

Создание представления:
Добавлено представление Index.cshtml в папку Views/HelloWorld/.
В файле Index.cshtml добавлен простой HTML-код с сообщением.

Работа с макетом:
Изменён файл макета _Layout.cshtml (например, заменено "MvcMovie" на "Movie App").
Обновлены заголовки и ссылки в макете.
Передача данных в представление:
В методе Welcome контроллера данные (name и numTimes) передаются в представление через ViewData.
Создано представление Welcome.cshtml, которое использует переданные данные для вывода списка сообщений.

Итог:
Теперь приложение использует Razor-представления для генерации HTML.
Данные передаются из контроллера в представление через ViewData.
Общий макет сайта применён ко всем страницам.