# Лекция 3

__Аналоговый (непрерывный) сигнал__ – непрерывное
изменение во времени физической величины
(напряжение, ток, температура, амплитуда звука и т.п.)

При передаче аналогового сигнала необходимо иметь ввиду, что передается не сам сигнал, а некоторый моделированный, наложенный на высокочастотный, который 
называется __несущим__

Таким образом у нас есть несущий сигнал, модулирующий и результат их наложения называется __мудулированным сигналом__.

Аналоговые сигналы могут передоваться:

1. по одиночному проводнику
2. по дифференциальной паре
3. по оптоволокну



# Передача аналоговых сигналов:

## VGA-кабель

_(одиочный проводник)_

У него есть 3 основных (красный, зеленый и синий) компоненты, которые передают в диапазоне -0.7В и задают интенсивность того или иного компонента цвета, который отображается на мониторе.

Для передачи на большие расстояния необходимо делать оплетку кабелей, его используют до 10 метров, а дальше необходимы кабели с усилителями. 

Плюс: если уничтожить один провод,то просто потеряется компонента какого-то цвета, но изображение останется, так как передача аналоговая. 
(Если рассматривать DVI, то при откусывании одного провода показываться на экрани ничего не будет, так как передача дискретная и просто нарушится протокол данных)

### Распиновка

![image](https://user-images.githubusercontent.com/27426287/112726163-109da800-8f2d-11eb-9aa9-66adf3a83e3d.png)


![image](https://user-images.githubusercontent.com/27426287/112726152-0380b900-8f2d-11eb-91c0-1d89732ccf02.png)



## Коаксиальный кабель

Чаще всего, если мы хотим использовать для передачи данных одиночный проводник, используется коаксиальный кабель. 
По нему можно передовать данные на большие расстояния.

По нему идет телевидение к телевизору, подключаются разные антенны.

Коаксиальный каель состоит из 4-х компонент:

1. проводник 
2. изоляция
3. экран
4. внешняя изоляция

![image](https://user-images.githubusercontent.com/27426287/112726310-c668f680-8f2d-11eb-8fcd-812a2a48a385.png)

![image](https://user-images.githubusercontent.com/27426287/112726465-b998d280-8f2e-11eb-9da7-df9ddd4475c5.png)

Экран необходим, чтобы не было никакого влияния внешних электромагнитных помех на проводник. 
Экран может быть сделан из полиэтилена, фторопласта, в специальных кабелях там может быть воздух

Изоляция необходима для защиты от внешних воздействий. В современных кабелях делается двойная оплетка из фольги и оплетки из жилок, 
служащей для придания и механической жесткости и для связывания экрана, поскольку фольга не сваренная, а просто обернута вокруг. 

Сигнал движется между оплеткой и центральной жилой: там возникает напряжение и возникает ток, текущий по внешней поверхности центрального проводника 
и по внутренней поверхности оплетки.

Для подключения используются SMA-разъемы. У эти разъемов есть центральная жила, которая является пазом для штыря, а экран подключается к внешнему радиусу 
(внешнему кольцу).

![image](https://user-images.githubusercontent.com/27426287/112726427-7b031800-8f2e-11eb-9d3e-d20afecc1e13.png)



## Дифференциальная пара

Сначала сигнал передпется по одному проводнику, а потом раздваивается, затем сигнал раздваивается и по одному проводнику передается в обычном виде, по другому - в инвертированном, потом идет в канал передачи данных. Если в канале есть помеха, то она одинакого влияет на одну и другую составляющую и ее можно определить для получения исходного сигнала   

![image](https://user-images.githubusercontent.com/27426287/112726885-b43c8780-8f30-11eb-9055-4d5f56f281b3.png)

Этот принцип используется для передачи данных на большие расстояния. Чаще всего он используется в витой паре.  

![image](https://user-images.githubusercontent.com/27426287/112726950-08476c00-8f31-11eb-9874-4fd6bfeecb4e.png)

В одной витой паре много витых проводников. Чем больше проводников - тем выше скорость передачи.



## Оптоволокно

По строению похоже на коаксиальный кабель, только в качестве центральной жили используются оптические волокна (стекло, керамика). При передачи цифрового сигнала: есть свет, нет света. При передачи аналого сигнала меняются параматры света, как волны (частота, фаза). В некоторых каналах передачи связи даже используются одиночные фотоны - это называется квантовые каналы (сигнал - совокупность частиц, имеющих какие-то параметры).

![image](https://user-images.githubusercontent.com/27426287/112726983-39c03780-8f31-11eb-8188-860c0b2f90cc.png)

Для передачи данных используются специальные модули, которые переводят напряжение или ток в свет, и используются коннекторы (сверху слева).



# Передача цифровых сигналов

Также передаются по одиночному проводнику, дифференциальной паре или оптоволокну. 

## Стандарты передачи цифровых сигналов

### Однополярные сигналы: 

1. TTL
2. CMOS
3. LVCMOS

![image](https://user-images.githubusercontent.com/27426287/112727539-003cfb80-8f34-11eb-872a-83e0363c1420.png)

Есть 2 типа логики: TTL, в основе которых лежат биполярные транзисторы и CMOS на полевых. Сейчас в основном используется CMOS логика - потому что она быстрее переключается, меньше потребляет и можно транзисторы изготавливать меньшего размера. 

LVCMOS - это низковольтная CMOS. 



## Дифференциальная пара

Основные стандарты:

- LVPECL
- VML
- CML
- LVDS

![image](https://user-images.githubusercontent.com/27426287/112727858-93c2fc00-8f35-11eb-8209-880e01a3ce46.png)

Чаще всего в цифровой технике используется LVDS, так как он приспособлен для быстрой передачи цифровых сигналов и меньше потребляет. В некоторых случаях в зависимость от конструкции приема-передачи оправдано использование дургих стандартов. Все перечисленные стандарты можно конвертировать друг в друга. 

В стандартах LVPECL, CML, LVDS используется направление тока, а в VML - напряжение.

На платах можно встретить рисунки: 

![image](https://user-images.githubusercontent.com/27426287/112728246-6414f380-8f37-11eb-9c24-f8b22728f1b4.png)

Это нужно для того, чтобы выровнять длинну проводников и гарантировать, что сигналы придут в одно и тоже время, что очень важно для дискретных сигналов.


## PECL/LVPECL

Линии 3.3 В, строится на биполярных транзисторах и схеме эмитторного повторителя. Информационным параметром является ток, который идет в линию передач и уходит с иннитора.

![image](https://user-images.githubusercontent.com/27426287/112728449-662b8200-8f38-11eb-9043-815958294a23.png)


- Состоит из дифференциальной пары, которая управляет
парой эмиттерных повторителей

- Выход эмиттерных повторителей должен работать в
активном регионе, с текущим непрерывно постоянным
током

- Интерфейс PECL подходит как для +5.0V, так и для +3.3V
напряжений питания. Когда напряжение питания +3.3V,
такой интерфейс обычно называют LVPECL.

- У пекла лучше фронты, чем у лвдс при передаче информации по проводу (при передачи внутри печатный платы лучше использовать LVDS)


## LVDS

Основной принцып кодирования не в исле тока, а в его направлении. При помощи 100-Омного резистора определяется направление, в приемнике ток преобразуется в напряжение.

Схема LVDS-передатчика представляет собой сбалансированный
источник тока, положительные и отрицательные сигналы которого
сдвинуты на 180° и совместно создают выходное
дифференциальное напряжение.

![image](https://user-images.githubusercontent.com/27426287/112728694-8c055680-8f39-11eb-8ca0-58ac471b6866.png)


## CML

CML - логические схемы на переключателях тока. Ключи типичного
выходного каскада нагружены на резисторы 50 Ом и подтянуты к V_CC.

Используется редко, ее заменяют PECLом. Используется когда необходимо организоывть токовую передачу. 

![image](https://user-images.githubusercontent.com/27426287/112728749-d090f200-8f39-11eb-9b44-3cf129a8e99e.png)

## VML

VML - логические схемы
на переключателях
напряжения.

Состоит из двухтактных выходных каскадов, 0 и 1 передаются дифференциально, информационный сигнал кодируется напряжением.  

![image](https://user-images.githubusercontent.com/27426287/112728772-e69eb280-8f39-11eb-9b92-b8397d9c44d9.png)

### Итог

Сейчас большинство работает по стандартам LVPECL и LVDS - первым передаются какие-нибудь сигналы синхронизации, где важна точность фронтов, точность передачи самого сигнала, а с помощью второго передаются уже данные, когда важна скорость и четкость переключение между 0 и 1

## Сопряжение дифференциальных пар

![image](https://user-images.githubusercontent.com/27426287/112728938-b73c7580-8f3a-11eb-8aae-943b7f6d0fcb.png)

При сопряжении с постоянной составляющей можно сопрягать напрямую

При сопряжении по линии с переменной составляющей есть разрыв связи для избежания передачи помех на стороне передатчика, передача происходит при помощи конденсатора.

## Индустриальные разъемы 

используются на всякой спец. технике, имеют защиту от влаги, грязи, выдерживают высокие нагрузки и разную температуру  

![image](https://user-images.githubusercontent.com/27426287/112729074-69743d00-8f3b-11eb-9b03-76aa2c979c6d.png)


## USB type-C

__недосатки:__

- негерметичность (боится пыли и влаги)

- некачественность линий, которые могут сложиться в гармошку в недорогих разъемах

__преимущества:__

- удобен
- можно вставлять разной стороной 
- нет креплений (если случайно сильно дернуть провод, он просто выпадет)

## DVI-разъем 

__недосатки:__

- прикручивается 
- часто гнутся штыри


