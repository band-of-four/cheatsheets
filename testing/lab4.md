# Тестирование системы целиком  - системное тестирование

Системное тестирование программного обеспечения — это тестирование ПО, выполняемое на полной, интегрированной системе, с целью проверки соответствия системы исходным требованиям. Системное тестирование относится к методам тестирования чёрного ящика, и, тем самым, не требует знаний о внутреннем устройстве системы.

Задача: проверка как функциональных и не функциональных требований в системе в целом. 

При этом выявляются дефекты, такие как неверное использование ресурсов системы, непредусмотренные комбинации данных пользовательского уровня, несовместимость с окружением, непредусмотренные сценарии использования, отсутствующая или неверная функциональность, неудобство использования и т.д. Для минимизации рисков, связанных с особенностями поведения системы в той или иной среде, во время тестирования рекомендуется использовать окружение максимально приближенное к тому, на которое будет установлен продукт после выдачи.

- на базе требований (requirements based)
- на базе случаев использования (use case based)

Включает несколько фаз:

- Системное тестирование — выполняется внутри организации-разработчика
- Альфа- и Бета-тестирование — выполняется пользователем под контролем разработчика
- Приемочное тестирование — выполняется пользователем.

# Тестирование возможностей, стабильности, отказоустойчивости, совместимости

Относится к нефункциональному тестированию.

__Тестирование возможностей__ - минимальная нагрузка, состоящая из корректных и реальных данных, проверка возможностей и функционала системы.

__Тестирование стабильности__ - добавляем нагрузку, данные всё еще корректны. Проверяем как система работает в более-менее реальных условиях

__Тестирование отказоустойчивости__ - пытаемся всё сломать к чертям. Некорректные данные, большая нагрузка, сбои питания, восстановление после отказа и т.д.

__Тестирование совместимости__ - запуск с различными версиями библиотек, на различном окружении. Смотрим как система со всем этим работает.

# Тестирование производительности - CARAT

CARAT -- подход к нагрузочному тестированию.

_Capacity_ — Нефункциональные возможности (Максимальное количество (пользователей,
записей в БД, файлов, Кб, ГГц), поддерживаемое системой одновременно, не нарушая других
требований производительности
)

_Accuracy_ — Точность -- корректность алгоритмов и результатов.

_Responce Time_ — Время ответа -- время ответа сервиса при разных видах нагрузки.

_Availability_ — Готовность -- способность сервиса обслуживать клиента.

_Throughput_ — Пропускная способность -- количество операций в секунду, которое может поддерживать система.

# Альфа и Бета тестирование. Приемочное тестирование

__Альфа-тестирование__ — имитация реальной работы с системой штатными разработчиками, либо реальная работа с системой потенциальными пользователями/заказчиком.

Альфа-тестирование - проводится небольшим количеством пользователей внутри организации, разработавшей ПО.

– Может проводиться до окончания системного тестирования
– Ранние отзывы пользователей об использовании системы в рабочем окружении

__Бета-тестирование__ — в некоторых случаях выполняется распространение предварительной версии (в случае проприетарного программного обеспечения иногда с ограничениями по функциональности или времени работы) для некоторой большей группы лиц с тем, чтобы убедиться, что продукт содержит достаточно мало ошибок. Иногда бета-тестирование выполняется для того, чтобы получить обратную связь о продукте от его будущих пользователей.

- Могут быть ошибки
- Может быть не реализован весь функционал
- Ранние отзывы для разработчиков
- Превью для пользователей


__Приёмочное тестирование__ - формальный процесс тестирования, который проверяет соответствие системы требованиям и проводится с целью: определения удовлетворяет ли система приемочным критериям; вынесения решения заказчиком или другим уполномоченным лицом принимается приложение или нет.

# Нагрузочное тестирование - виды, цели и решаемые задачи.

__Тестирование производительности__ (Performance testing) - это автоматизированное тестирование, имитирующее работу определенного количества бизнес пользователей на каком-либо общем ресурсе.

Задача - определение масштабируемости приложения под нагрузкой, при этом происходит:

- измерение времени выполнения выбранных операций при определенных интенсивностях выполнения этих операций
- определение количества пользователей, одновременно работающих с приложением
- определение границ приемлемой производительности при увеличении нагрузки (при увеличении интенсивности выполнения этих операций)
- исследование производительности на высоких, предельных, стрессовых нагрузках

__Стрессовое тестирование__ (Stress Testing) - позволяет проверить насколько приложение и система в целом работоспособны в условиях стресса и также оценить способность системы к регенерации, т.е. к возвращению к нормальному состоянию после прекращения воздействия стресса. 

__Объемное тестирование__ (Volume Testing) - Задачей объемного тестирования является получение оценки производительности при увеличении объемов данных в базе данных приложения, при этом происходит:

- измерение времени выполнения выбранных операций при определенных интенсивностях выполнения этих операций
- может производиться определение количества пользователей, одновременно работающих с приложением

__Тестирование стабильности или надежности__ (Stability / Reliability Testing) - проверка работоспособности приложения при длительном (многочасовом) тестировании со средним уровнем нагрузки. При этом на первое место выходит отсутствие утечек памяти, перезапусков серверов под нагрузкой и другие аспекты влияющие именно на стабильность работы.

# Принципы реализации нагрузочного тестирования ПО.


# Инструменты для реализации нагрузочного тестирования.

<table class="wikitable">

<tbody><tr>
<th>ПО
</th>
<th>Наименование производителя
</th>
<th>Комментарии
</th></tr>
<tr>
<td><a href="/wiki/OpenSTA" title="OpenSTA">OpenSTA</a>
</td>
<td>'Open System Testing Architecture'
</td>
<td>Свободно распространяемое программное обеспечение для нагрузочного/стресс тестирования, лицензированное GNU GPL. Использует распределённую архитектуру приложений, основанную на <a href="/wiki/CORBA" title="CORBA">CORBA</a>. Доступна версия под Windows, хотя имеются проблемы с совместимостью с Windows Vista. Поддержка прекращена в 2007 году.
</td></tr>
<tr>
<td>IBM Rational Performance Tester
</td>
<td>IBM
</td>
<td>Основанное на среде разработки <a href="/wiki/Eclipse_(%D1%81%D1%80%D0%B5%D0%B4%D0%B0_%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8)" title="Eclipse (среда разработки)">Eclipse</a> ПО, позволяющее создавать нагрузку больших объёмов и измерять время отклика для приложений с клиент-серверной архитектурой. Требует лицензирования.
</td></tr>
<tr>
<td><a href="/wiki/JMeter" title="JMeter">JMeter</a>
</td>
<td>Открытый проект Apache Jakarta Project
</td>
<td>Основанный на Java кроссплатформенный инструментарий, позволяющий производить нагрузочные тесты с использованием JDBC / FTP / LDAP / SOAP / JMS / POP3 / HTTP / TCP соединений. Даёт возможность создавать большое количество запросов с разных компьютеров и контролировать процесс с одного из них.
</td></tr>
<tr>
<td><a href="/wiki/HP_LoadRunner" title="HP LoadRunner">HP LoadRunner</a>
</td>
<td>HP
</td>
<td>Инструмент для нагрузочного тестирования, изначально разработанный для эмуляции работы большого количества параллельно работающих пользователей. Также может быть использован для <a href="/wiki/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%D0%BD%D0%BE%D0%B5_%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5" title="Модульное тестирование">unit-</a> или <a href="/wiki/%D0%98%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%BE%D0%BD%D0%BD%D0%BE%D0%B5_%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5" title="Интеграционное тестирование">интеграционного тестирования</a>.
</td></tr>
<tr>
<td><a href="/w/index.php?title=LoadComplete&amp;action=edit&amp;redlink=1" class="new" title="LoadComplete (страница отсутствует)">LoadComplete</a>
</td>
<td>SmartBear
</td>
<td>Проприетарный продукт, позволяющий проводить нагрузочное тестирование веб-приложений
</td></tr>
<tr>
<td><a href="/wiki/Silk_Performer" title="Silk Performer">SilkPerformer</a>
</td>
<td><a href="/wiki/Micro_Focus" title="Micro Focus">Micro Focus</a> (Borland)
</td></tr>
<tr>
<td>Siege
</td>
<td>Joe Dog Software
</td>
<td>Siege&nbsp;— это утилита для нагрузочного тестирования веб-серверов.<sup id="cite_ref-3" class="reference"><a href="#cite_note-3">[3]</a></sup>
</td></tr>
<tr>
<td><a href="/wiki/Microsoft_Visual_Studio" title="Microsoft Visual Studio">Visual Studio</a> Team System
</td>
<td><a href="/wiki/Microsoft" title="Microsoft">Microsoft</a>
</td>
<td>Visual Studio предоставляет инструмент для тестирования производительности включая load / unit testing
</td></tr>
<tr>
<td>QTest
</td>
<td>Quotium
</td>
<td>
</td></tr>
<tr>
<td>HTTPerf
</td>
<td>
</td>
<td>
</td></tr>
<tr>
<td>QALoad
</td>
<td>Compuware Ltd.
</td></tr>
<tr>
<td>(The) Grinder
</td>
<td>
</td>
<td>
</td></tr>
<tr>
<td><a href="/wiki/WebLOAD" title="WebLOAD">WebLOAD</a>
</td>
<td><a href="/w/index.php?title=RadView_Software&amp;action=edit&amp;redlink=1" class="new" title="RadView Software (страница отсутствует)">RadView Software</a>
</td>
<td>Нагрузочное тестирование инструмент для веб-и мобильных приложений, включая веб-панели для тестирования производительности анализа. Используется для крупномасштабных нагрузок, которые могут быть сгенерированы также из облака. лицензированный.<sup id="cite_ref-4" class="reference"><a href="#cite_note-4">[4]</a></sup>
</td></tr></tbody></table>

# Apache JMeter - архитектура, поддерживаемые протоколы, особенности конфигурации.

Как эта фигня работает - создает http запросы, эмулируя поведение заданного количества пользователей, посылает их приложению, сохраняет все ответы и анализирует.
Thread Group – Описывает пул пользователей для выполнения теста – Количество, возрастание и пр.. 

Семплеры – Формируют запросы, генерируют результаты – Большой набор встроенных протоколов (TCP, HTTP, FTP, JDBC, SOAP, JMS, SMTP, …..)

Логические контроллеры – Определяют порядок вызова семплеров – Конструкции управления (if, loop, …) – Управление потоком 

Слушатели – Получают ответы – Осуществляют доп. операции с результатами: просмотр, запись, чтение и др. – Не обрабатывают данные! (в командной строке, нужен GUI)

Таймеры – Задержки между запросами – Постоянные, в соответствии с законами 

Аssertion – Проверяют результаты 

Элементы конфигурации – Сохраняют предустановленные значения для семплеров 

Препроцессоры – Изменяют семплеры в их контексте (HTML Link Parser)

Постпроцессоры – Применяются ко всем семплерам в одном контексте

## Порядок выполнения:

1. Конфигурационные элементы
2. Препроцессоры
3. Таймеры
4. Семплеры
5. Постпроцессоры
6. Assertions
7. Слушатели

# Стресс-тестирование - основные понятия, виды стресс-сценариев.

Стресс-тестирование - обычно последовательная нагрузка системы до момента неприемлемого значения характеристик, позволяют определить критические значения входных параметров,
а также характеристики системы в аварийном режиме и количество времени которое необходимо для восстановления (если оно происходит).

Основные виды сценариев:

1. Общее исследование поведения системы при пиковых нагрузках.
2. Исследование обработки ошибок и исключительных ситуаций системой при пиковых нагрузках.
3. Исследование узких мест системы или отдельных компонент при диспропорциональных нагрузках.
4. Тестирование ёмкости системы.

# Стресс-тестирование ПО. Виды стресс-тестов ПО. Тестирование ёмкости.

Виды описаны в предыдущем вопросе.

Тестирование емкости: тестирование с целью определить запас прочности системы при полном соответствии требованиям производительности (по сути когда мы определяем сколько
пользователей максимально поддерживает система оставаясь в рамках необходимого времени ответа в лабе). Как результат получаем набор максимально допустимых характеристик нагрузки
системы, при которых она удовлетворяет требованиям, заданным на этапе проектирования.
