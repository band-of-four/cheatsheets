[Вопросы отсюда](https://picloud.pw/media/resources/posts/2018/02/20/Рубежка_1_Билеты_2017.txt)


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

JS-функция, открывающая в новом окне браузера сайт http://www.google.com

```js
window.open("http://google.com", "newwin", "width=1200,height=600");
```

Реализовать функцию на JavaScript, которая будет закрывать текущее окно, если в нем открыт https://www.google.ru

```js
function close_window() {
  if (window.location.href===”https://www.google.ru”) {
	window.close();
  }
}
```

JS-функция, удаляющая со страницы все элементы <div> c классом “MarkedToRemove”
	
```js
Array.prototype.slice.call(document.getElementsByTagName("div")).forEach(function (e) {
   if (e.getAttribute("class") === "MarkedToRemove"){
       e.parentNode.removeChild(e);
   }
});
```



# Задания с CSS

 Правило css, меняющее цвет фона на желтый, если ссылка посещена и не лежит в классе "news"

```css
a:visited:not([class*="news"]) {
	background: yellow;
}
```

Написать css правило, которое при клике на ссылку добавляет ей подчеркивание, всем кроме ссылок в теге h1

```css
a:not(h1) :visited, :active {
	text-decoration: underline;
}
```

css правило, выравнивающее все блоки <div> внутри формы с id=”sampleForm” по правому краю

```css
#sampleForm div{
text-align:right
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
```

Код фильтра запросов, запрещающий доступ к приложению неавторизированным пользователям(у неавт пол в запросе отсутствует заголовок x-application-user

```java
public class TestFilter implements Filter {

    @Override
    public void init(FilterConfig filterConfig) throws ServletException {
    }

    @Override
    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {

        HttpServletRequest httpServletRequest = (HttpServletRequest) servletRequest;

        if(httpServletRequest.getHeader("x-application-user") == null){
            httpServletRequest.getRequestDispatcher("/").forward(servletRequest, servletResponse);
        }

        filterChain.doFilter(servletRequest, servletResponse);
    }

    @Override
    public void destroy() {

    }
}
```

Написать сервлет, который будет возвращать все запросы на переадресацию на сайт google.com

```java
public class RedirectServlet extends HttpServlet {
	RedirectFilter filter = new RedirectFilter;
	public void service(HttpServletRequest request, HttpServletResponse response) throws IOExeption, ServletException {
		filter.doFilter(request, response);
		int status = response.getStatus();
		if (status == 302) {
			response.sendRedirect("http://google.com");
		}
	}
}
```

# JSP

Страница JSP, проверяющая есть ли /какой-то параметр/ в запросе и если нету  выводящая сообщение об ошибке

```jsp
 <%
if(request.getAttribute(“123”)==null){
	String error = "Please set '123' param";
}
%>
<p>${error}</p>
```
