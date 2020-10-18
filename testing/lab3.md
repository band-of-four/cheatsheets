# Вопросы с se ifmo

## Функциональное тестирование. 

Функциональное тестирование — это тестирование ПО в целях проверки реализуемости функциональных требований, то есть способности ПО в определённых условиях решать задачи, нужные пользователям.

### Основные понятия 

???

### Cпособы организации

- На базе сценариев использования
- Ручное/автоматическое
- На готовой системе, в рамках модульного и интеграционного
- Проверяются функции системы начиная с интерфейса пользователя
- Средства автоматизации
  + Открытые: Selenium, Sahi, Watir
  + Коммерческие: от HP, Rational (IBM)
- На основе функционмльных требований,указанных в спецификации / на основе бизнесс-процессов
- 

### Pешаемые задачи.

подтверждение того, что разрабатываемый программный продукт обладает всем функционалом, требуемым заказчиком.



## Система Selenium. 

### Архитектура 

#### Selenium RC

работает только с использованием JavaScript для каждой команды. Это означает, что все, что вы пишете, в конечном итоге переводится в Javascript и запускается в браузере.

Плюсы:

- как правило работает одинакого для браузера

Минусы:

- Устарел
- Ограничевается возможностями JS и  same-origin policy (веб-браузер разрешает сценариям, содержащимся на первой веб-странице, получать доступ к данным на второй веб-странице, но только если обе веб-страницы имеют одинаковое происхождение.)

#### WebDriver 

WebDriver фактически использует собственный и родной API каждого браузера для работы с ними

Плюсы:

- Быстрее
- Более гибкий

Минусы:

- может работать по-разному в каждом браузере
- могут возникать ошибки при обновлении браузеров

#### Selenium IDE

Selenium WebDriver — это инструмент для автоматизации действий веб-браузера. 

Ограничения:

- Слабо развитое управление логикой теста
(циклы, условия, ….)
- Запускает только свои сценарии
- Сложно использовать с динамическим
содержимым

#### Selenium GRID

Selenium Grid позволяет выполнять сценарии WebDriver на удаленных машинах (виртуальных или реальных) путем маршрутизации команд, отправляемых клиентом, в удаленные экземпляры браузера. Его цель - предоставить простой способ запускать тесты параллельно на нескольких машинах.

### Принципы написания сценариев

Selrnium IDE

Команды:

- `clic`k или `clickAndWait` — ссылки,
переключатели, radio-кнопки
- `type` — ввод значений
- `select` — выбор значений из списка
- `оpen` — открывает страницу
- `assert***`
- `wait***` - ожидание события
- `verify ***` - проверка

Assert vs verify

- Предназначены для проверки содержимого
элемента UI
- Если `verification` неуспешна — тест
продолжается
- Если неуспешна `assertion` — тест
останавливается

Синхронизация:

- `waitForPageLoad(timeout`) загрузка страницы
 ошибка по таймауту
- `waitForAlert`
- `waitForTable` — полная загрузка таблицы
- `waitForTitle` — загрузка заголовка
- Другие команды синхронизации

Другие:

- `store` — сохранение значений в переменной
- `echo` — запись значения в лог selenium
– Можно использовать `${var}`

### Cпособы доступа к элементам страницы.

По XPath (относительный/абсолютный путь)

По id

По scc-правилам

## Язык XPath. 

<table class="table table-striped table-bordered table-hover"><thead><tr><th width="20%">Выражение</th><th width="80%">Результат</th></tr></thead><tbody><tr class="odd"><td><em>имя_узла</em></td><td>Выбирает все узлы с именем "имя_узла"</td></tr><tr class="even"><td>/</td><td>Выбирает от корневого узла</td></tr><tr class="odd"><td>//</td><td>Выбирает узлы от текущего узла, соответствующего выбору, независимо от их местонахождения </td></tr><tr class="even"><td>.</td><td>Выбирает текущий узел</td></tr><tr class="odd"><td>..</td><td>Выбирает родителя текущего узла</td></tr><tr class="even"><td>@</td><td>Выбирает атрибуты</td></tr></tbody></table>

#### Предикаты 

<table class="table table-striped table-bordered table-hover"><thead><tr><th width="20%">Выражение XPath</th><th width="80%">Результат</th></tr></thead><tbody><tr class="odd"><td>/messages/note[1]</td><td>Выбирает первый элемент note, который является прямым потомком элемента messages.
</td></tr><tr class="even"><td>/messages/note[last()]</td><td>Выбирает последний элемент note, который является прямым потомком элемента messages.</td></tr><tr class="odd"><td>/messages/note[last()-1]</td><td>Выбирает предпоследний элемент note, который является прямым потомком элемента messages.</td></tr><tr class="even"><td>/messages/note[position()&lt;3]
  </td><td>Выбирает первые два элемента note, которые являются прямыми потомками элемента messages.</td></tr><tr class="odd"><td>//heading[@date]</td><td>Выбирает все элементы heading, у которых есть атрибут date</td></tr><tr class="even"><td>//heading[@date="10/01/2008"]</td><td>Выбирает все элементы heading, у которых есть атрибут date со значением "10/01/2008"</td></tr></tbody></table>
  
#### Выбор неизвестных заранее узлов

<table class="table table-striped table-bordered table-hover"><thead><tr><th width="20%">Спецсимвол</th><th width="80%">Описание</th></tr></thead><tbody><tr class="odd"><td>*</td><td>Соответствует любому узлу элемента</td></tr><tr class="even"><td>@*</td><td>Соответствует любому узлу атрибута</td></tr><tr class="odd"><td>node()</td><td>Соответствует любому узлу любого типа</td></tr></tbody></table>

#### Выбор нескольких путей

<table class="table table-striped table-bordered table-hover"><thead><tr><th width="20%">Выражение XPath</th><th width="80%">Результат</th></tr></thead><tbody><tr class="odd"><td>//note/heading | //note/body</td><td>Выбирает все элементы heading И body из всех элементов note</td></tr><tr class="even"><td>//heading | //body</td><td>Выбирает все элементы heading И body во всем документе</td></tr></tbody></table>

#### Оси 

Ось определяет отношение узлового набора по отношению к текущему узлу.

<table class="table table-striped table-bordered table-hover"><thead><tr><th width="20%">Название оси</th><th width="80%">Результат</th></tr></thead><tbody><tr class="odd"><td>ancestor</td><td>Выбирает всех предков текущего узла</td></tr><tr class="even"><td>ancestor-or-self</td><td>Выбирает всех предков текущего узла и сам текущий узел</td></tr><tr class="odd"><td>attribute</td><td>Выбирает все атрибуты текущего узла</td></tr><tr class="even"><td>child</td><td>Выбирает всех прямых потомков текущего узла</td></tr><tr class="odd"><td>descendant</td><td>Выбирает всех потомков текущего узла</td></tr><tr class="even"><td>descendant-or-self</td><td>Выбирает всех потомков текущего узла и сам текущий узел</td></tr><tr class="odd"><td>following</td><td>Выбирает все элементы в документе после закрывающего тега текущего узла</td></tr><tr class="even"><td>following-sibling</td><td>Выбирает все элементы одного уровня после текущего узла</td></tr><tr class="odd"><td>namespace</td><td>Выбирает все узлы пространства имен текущего узла</td></tr><tr class="even"><td>parent</td><td>Выбирает родителя текущего узла</td></tr><tr class="odd"><td>preceding</td><td>Выбирает все узлы, которые появляются перед текущим узлом, за исключением предков, узлов атрибутов и пространства имен</td></tr><tr class="even"><td>preceding-sibling</td><td>Выбирает все элементы одного уровня до текущего узла</td></tr><tr class="odd"><td>self</td><td>Выбирает текущий узел</td></tr></tbody></table>

#### Операторы

<table class="table table-striped table-bordered table-hover"><thead><tr><th width="20%">Оператор</th><th width="50%">Описание</th><th width="30%">Пример</th></tr></thead><tbody><tr class="odd"><td>|</td><td>Обрабатывает два узловых набора</td><td>//note | //cd</td></tr><tr class="even"><td>+</td><td>Сложение</td><td>5 + 7</td></tr><tr class="odd"><td>-</td><td>Вычитание</td><td>7 - 5</td></tr><tr class="even"><td>*</td><td>Умножение</td><td>9 * 5</td></tr><tr class="odd"><td>div</td><td>Деление</td><td>4 div 3</td></tr><tr class="even"><td>=</td><td>Равно</td><td>lang=6.90</td></tr><tr class="odd"><td>!=</td><td>Не равно</td><td>lang!=4.50</td></tr><tr class="even"><td>&lt;</td><td>Меньше</td><td>ret&lt;7.10</td></tr><tr class="odd"><td>&lt;=</td><td>Меньше или равно</td><td>terra&lt;=9.80</td></tr><tr class="even"><td>&gt;</td><td>Больше</td><td>root&gt;2.55</td></tr><tr class="odd"><td>&gt;=</td><td>Больше или равно</td><td>last&gt;=4.30</td></tr><tr class="even"><td>or</td><td>Или</td><td>step=10 or loop=7.70</td></tr><tr class="odd"><td>and</td><td>И</td><td>loop&gt;6.00 and loop
</td></tr><tr class="even"><td>mod</td><td>Остаток от деления</td><td>5 mod 2</td></tr></tbody></table>
