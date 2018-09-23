# Интернационализация. Локализация. Хранение локализованных ресурсов.

__Интернационализа́ция__ — проектирование программы таким образом, чтобы локализация была возможна без конструктивных изменений.
выделение текстовых данных из кода, отображение данных с учетом местных форматов

__Локализация__ - процесс адаптации программного обеспечения к культуре какой-либо страны.
перевод текстов, использование соответствующих форматов данных, замена звуковой и визуальной информации

## Хранение локализованных ресурсов:
 
### ListResourceBundle

```java
ListResourceBundle абстрактный подкласс ResourceBundle, который управляет ресурсами для локализации используя List, находящийся в классе. Ресурсы хранятся в классе-наследнике ListResourceBundle, в котором необходимо переопределить getContents и создать массив, в котором каждому элементу соответствует пара объектов “ключ”-”значение”.
	 public class MyResources extends ListResourceBundle {
		protected Object[][] getContents() {
			return new Object[][] = { /*...*/ }
		}
}
public class MyResources_fr extends ListResourceBundle {
     protected Object[][] getContents() {
         return new Object[][] = { /*...*/}
     }
}
```

### PropertyResourceBundle

PropertyResourceBundle абстрактный подкласс ResourceBundle, который управляет ресурсами для локализации,  используя ряд статических строк из файла свойств.  ResourceBundle.getBundle будет автоматически искать соответствующий файл свойств и создавать a PropertyResourceBundle 

# Форматирование локализованных числовых данных, текста, даты и времени. Классы NumberFormat, DateFormat, MessageFormat, ChoiceFormat.

## Форматирование числовых данных:
Класс  java.text.NumberFormat предназначен для форматирования чисел. Это абстрактный класс, экземпляры которого можно получить с помощью методов getInstance(): 

```java
public static final NumberFormat getInstance()

public static NumberFormat getInstance(Locale inLocale)
```

Полученный экземпляр NumberFormat  можно использовать для форматирования чисел с помощью метода format  и парсинга чисел с помощью метода parse:

```java
String str1 = java.text.NumberFormat.getInstance().format(10_000_000.34);
``` 

Класс java.text.DecimalFormat расширяет класс java.text.NumberFormat. Содержит дополнительно два конструктора, принимающих строку с форматом числа:

```
public DecimalFormat(String pattern)
public DecimalFormat(String pattern, DecimalFormatSymbols symbols)
```

DecimalFormatSymbols, позволяет полностью настроить форматирование числа. Pattern  содержит шаблон, который может содержать специальные символы:

## Форматирование даты и времени:

### Класс java.text.DateFormat. 

Для получения экземпляра класса: 

```java
public  static final DateFormat getInstance()
public static final DateFormat getDateInstance()    // дата без времени
public static final DateFormat getDateInstance(int style*)
public static final DateFormat getDateInstance(int style, Locale locale)

public static final DateFormat getTimeInstance()    //время без даты
public static final DateFormat getDateTimeInstance() //и дата и время
```

*Style: DateFormat.FULL, DateFormat.LONG, DateFormat.SHORT, DateFormat.MEDIUM, DateFormat.DEFAULT.

### Форматирование и парсинг также происходит с помощью методов format  и parse .

Класс java.text.SimpleDateFormat наследуется от java.text.DateFormat  и позволяет указать пользовательский шаблон форматирования. (G - эра, y - год, … ) 

### Форматирование текста:

Класс MessageFormat: форматирует текст, содержащий фрагменты, представленные в виде переменных.

`Solar_en.properties`

msg = {0} solar eclipse will be at {1,time,short} on {1,date,short}.

Статический метод MessageFormat.format() позволяет подставить значение переменных.

### Класс ChoiceFormat:
    
```java    
    double limits[] = { 0.0, 0.1, 0.3, 0.7 };
    String labels[] = { "very low", "low", "moderate", "high" };
    ChoiceFormat format = new ChoiceFormat(limits, labels);
    System.out.println(format.format(r) + " (" + r + ").");
//r == 0.0    very low(0.0)
//r == 0.1     low(0.1)
//r == 0.3    moderate(0.3)
//r == 0.7    high(0.7)
```

# Классы для представления даты и времени из пакета java.time. Преобразование темпоральных величин.

## Класс Date:

Методы:  boolean after(Date date), boolean before(Date date), long getTime() - возвращает количество миллисекунд, прошедших с 1 января 1970 года

Почти все методы объявлены deprecated

## Класс TimeZone: 

Временная зона GMT и UTC

## Класс: Calendar: 

Абстрактный класс — преобразование из машинных в
человеческие единицы

java.time — основной пакет для работы с датой и
временем

- java.time.chrono — календарные системы
- java.time.format — классы для форматирования
- java.time.temporal — преобразования времени и вычисления
- java.time.zone — работа с поясным временем

# statement, prepared statement, callable statement

Объект Statement используется для выполнения SQL-запросов к БД. Существует три типа объектов Statement. Все три служат как бы конейнерами для выполнения SQL-выражений через данное соединение: Statement, PreparedStatement,, и CallableStatement. Они специализируются на различных типах запросов: Statement используется для выполнения простых SQL-запросов без параметров; PreparedStatement используется для выполнения прекомпилированных SQL-запросов с или без входных (IN) параметров; CallableStatement используется для вызовов хранимых процедур.

SQL-выражения в PreparedStatement могут иметь один или более входной (IN) параметр. Входной параметр - это параметр, чье значение не указывается при создании SQL-выражения. Вместо него в выражении на месте каждого входного параметра ставится знак ("?"). Значение каждого вопросительного знака устанавливается методами setXXX перед выполнением запроса.

# Hebernate
__Hibernate__ – это ORM фреймворк для Java

Обеспечивает простой API для записи и получения Java-объектов в/из БД.

Минимизирует доступ к БД, используя стратегии fetching.

Не требует сервера приложения.

Позволяет нам не работать с типами данных языка SQL, а иметь дело с привычыми нам типами данных Java.

Заботится о создании связей между Java-классами и таблицами БД с помощью XML-файлов не внося изменения в программный код.

Если нам неоходимо изменить БД, то достаточно лишь внести изменения в XML-файлы.


# fetchType

Есть два варианта загрузки полей с отношением один-ко-многим: загрузить все объекты вместе с остальными полями ( FetchType.EAGER) или загрузить его по требованию ( FetchType.LAZY), когда вы вызываете метод  getИмяПоля().

Когда в университете много учеников, неэффективно загружать всех его учеников, когда они не нужны. Поэтому в подобных случаях вы можете заявить, что хотите, чтобы ученики загружались, когда они действительно нужны. Это называется ленивой загрузкой.
