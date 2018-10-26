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