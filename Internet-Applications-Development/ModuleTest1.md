[Вопросы отсюда](https://picloud.pw/media/resources/posts/2018/02/20/Рубежка_1_Билеты_2017.txt)

# Java SE, Java EE, Java ME

* Java SE — основные инструменты и библиотеки языка
* Java EE — платформа для enterprise серверных приложений (JSP, JSF, сервлеты и т.д.)
* Java ME — урезанная платформа для мобильных устройств (в основном использовалась до появления iOS/Android)

# Архитектура приложений Java EE, понятие о контейнере, компоненте

Сервлеты — серверные сценарии, жизненным циклом которых управляет веб-контейнер. Существует несколько
веб-контейнеров (Apache Tomcat, GlassFish, Jetty, др.); они все реализуют определенный стандарт Java EE (6/7/8).

При запуске веб-контейнер читает манифест (`web.xml`) приложения и создает для него `ServletContext`.
Для каждого класса сервлета и фильтра из манифеста создается объект. Контекст и объекты фильтров/сервлетов будут
жить на протяжении работы приложения, т.е. одна и та же инстанция будет использоваться для всех запросов и сессий.

При поступлении HTTP запроса веб-контейнер создает новые объекты `HttpServletRequest` и `HttpServletResponse`
и передает их фильтрам, потом сервлету.

# Задания на PHP

Написать скрипт, выводящий приветствие пользователю. Имя пользователя передается как get параметр:
```php
<?php
echo 'Hello ' . htmlspecialchars($_GET["name"]) . '!';
?>
```

Написать класс на PHP:
```php
class Fruit {
  protected $color = '';
}

class Orange extends Fruit {
  public function __construct(){
    $this->color = 'orange';
  }

  public function sayColor() {
    echo $this->color . "\n";
  }
}

$orange = new Orange();
$orange->sayColor();
?>
```

# Задания на JS

Написать функцию, которая на странице заменяет все тестовые поля ввода на кнопки:
```js
function replaceTextFields() {
  Array.prototype.slice.call(document.querySelectorAll('input[type=text]')).forEach(function(textField) {
    textField.setAttribute('type', 'submit');
  });
}
```

Написать функцию, которая запрещает писать числа и буквы латинского алфавита:
```js
document.querySelector('#textfield').onkeypress = function(e) {
  var input = e.key.toLowerCase();
  if (input >= 'a' && input <= 'z') return false;
  if (input >= '0' && input <= '9') return false;
  return true;
};
```

Написать функцию, которая заменяет содержимое `<div>` с именем класса `nyan` на изображение по ссылке: http://www.example.com/nyancat.gif:
```js
function insertNyancat() {
  document.querySelector('div.nyan').innerHTML = '<img src="http://www.example.com/nyancat.gif">';
}
```

Написать функцию, которая будет закрывать текущее окно, если в нем открыт https://www.google.ru:
```js
function leaveIfGoogle() {
  if (window.location.href.startsWith('https://www.google.ru'))
    window.close();
}
```
# Задания по сервлетам

Написать сервлет, который принимает из http запроса параметр name и выводит его. Если параметр не обнаружен то вывести Anonymous user
``` java
public class NameServlet extends HttpServlet {
  public void service(HttpServletRequest request,HttpServletResponse response) throws IOException, ServletException {
    PrintWriter out = response.getWriter();
    if (request.getParameter("name") != null ) {
      out.println(request.getParameter("name"));
    } else { 
      out.println("Anonymous user");
    }
  } 
}
'''
