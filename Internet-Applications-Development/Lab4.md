# Вопросы с se.ifmo.ru

## 2. Принципы IoC, CDI и Location Transpanency. Компоненты и контейнеры.

_Inversion of Control_: объекты создает не программист (используя `new`), а контейнер IoC. Применяется далеко не ко всем объектам в приложении, а только к управляемым
(в Spring это классы с аннотациями `@Component`, `@Service` и т.д., в EJB — бобы `@Stateless`, `@Stateful`, `@MessageDriven`).

Контейнер не только создает объекты, но полностью управляет их жизненным циклом, вызывая на определенных этапах callback методы.

_Dependency injection_:

Вместо построения зависимостей в компоненте, где они нужны:

```java
public class Something {
  private Dependency dependency = new Dependency()
}
```

Мы принимаем их извне, что избавляет компонент от необходимости управлять ими:

```java
public class Something {
  private Dependency dependency;

  public Something (Dependency dependency) {
    this.dependency = dependency;
  }
}  
```

Чтобы нам не пришлость вручную собирать все зависимости для создания компонентов,
контейнер IoC предоставляет возможность внедрения инстанций в поля, помеченные специальной аннотацией:

```java
public class SomethingDI {
  @Autowired private Dependency dependency; // Spring
  @EJB private EjbDependency ejbDependency; // EJB
}
```

## 5. Компоненты EJB. Stateless & Stateful Session Beans. EJB Lite и EJB Full.

EJB (Enterprise Java Bean) — спецификация.

Бобы делятся на _session beans_ (заседательные бобы) и _message driven beans_ (бобы, движимые посланиями).

_Session beans_ в свою очередь делятся на _stateful_ (у каждого клиента своя инстанция, в которой может хранится его состояние), _stateless_ (одна и та же инстанция обеспечивает запросы нескольких клиентов) и _singleton_ (одна инстанция на все приложение => общее для всех клиентов состояние).

_Message driven beans_ выполняют метод в ответ на получение сообщения из определенной очереди JMS.
