# SoftwareTesting
Выбранное для тестирования ПО - LibreOffice.  <br>
📁 Ссылка на скачивание: https://download.documentfoundation.org/libreoffice/stable/7.2.0/win/x86_64/LibreOffice_7.2.0_Win_x64.msi <br>
**Состав команды:**
* [Едапина Александра](https://github.com/Saaanyyyaa)
* [Кривошеева Виктория](https://github.com/vkkrvshv)
* [Крузина Алина](https://github.com/Alliion)
* [Муравлева Ульяна](https://github.com/uulyanamuur)

# Описание выбранного ПО 
LibreOffice — мощный офисный пакет, полностью совместимый с 32/64-битными системами. Переведён более чем на 30 языков мира. Поддерживает большинство популярных операционных систем, включая GNU/Linux, Microsoft Windows и Mac OS X. <br><br>

LibreOffice включает в себя следующие компоненты:
* Writer – многофункциональный текстовый процессор. Можно вставить в документ Writer изображения и объекты из других компонентов LibreOffice. Writer поддерживает экспорт файлов в форматы HTML, XHTML, XML, Adobe PDF и в несколько версий форматов Microsoft Word.
* Calc – табличный процессор, включающий в себя продвинутые средства для анализа, построения диаграмм и принятия решений. В распоряжении пользователя более 300 функций для финансовых, статистических и математических операций. Calc может экспортировать электронные таблицы в несколько форматов, включая, например, CSV, Adobe PDF и HTML.

* Impress - программа для создания презентаций. Impress интегрирован с компонентами LibreOffice Draw и Math. Слайд-шоу может быть дополнено специальными эффектами для текста, а также звуком и видеоклипами. Impress совместим с форматом файлов Microsoft PowerPoint и может сохранять презентацию в многочисленных графических форматах, включая Macromedia Flash (SWF) и Adobe PDF.

* Draw – инструмент для создания векторной графики, с помощью которого можно создавать простыe диаграммы, блок-схемы и даже сложную 3D-графику. Draw может открывать множество различных форматов файлов и сохранять результат в более чем 20 форматах, включая PNG, HTML, Adobe PDF и Flash.

* Base - простой интерфейс для ежедневной работы с базами данных. Можно создавать и редактировать формы, отчеты, запросы, таблицы, представления и связи, так же, как в других популярных приложениях для работы с базами данных. Base предоставляет возможность анализировать и редактировать связи в схеме представлений. Также Base включает в себя движок реляционной базы данных HSQLDB, но может использовать и другие движки: dBASE, Microsoft Access, MySQL или Oracle, или другие ODBC совместимые или JDBC совместимые базы данных. Base предоставляет поддержку для подмножества ANSI-92 SQL.

* Math – это инструмент для создания и редактирования формул в LibreOffice. Вы можете использовать его для создания сложных формул, которые включают в себя символы, недоступные в стандартных наборах шрифтов. Math обычно используется для создания формул в текстовых документах Writer и презентациях Impress, но может использоваться и как самостоятельный программный продукт. Созданные формулы можно сохранять в стандартном формате Mathematical Markup Language (MathML) для включения их в веб-страницы и другие документы, созданные не в LibreOffice.

# Диаграмма вариантов использования
<p align="center">
<img src="https://sun9-39.userapi.com/impg/gUzHVWxbLOnri_KnoxjHUNbN2p5ANUAvqxsCag/dP1cm7OxRnk.jpg?size=572x424&quality=96&sign=0cffa045c860ed46f74642f234a1aa8f&type=album">
</p>

# Найденные методом черного ящика баги
## `BUG №1 - Невозможность изменения цвета линии`
LibreOffice Writer предоставляет функцию рисования линии в документе, цвет которой по умолчанию синий. Для эсперимента было нарисовано несколько линий. При выделении линии и изменении цвета (на красный) всё работает, но если же попробовать изменить цвет линии на любой другой до того, как нарисовать её (в данном случае был выбран синий по умолчанию), ничего не поменяется, и линия останется того же цвета, который был использован последним.
![bug1](https://sun9-10.userapi.com/impg/KJYJo7PDC4OG74sI4yE7mmFB6ORkvUt5epOfBA/y7HU5DsQFfw.jpg?size=1920x1080&quality=96&sign=63dc6a517215db22ed9185c2ca8eeefb&type=album)
<br>
## `BUG №2 - Центр фигуры не смещается вместе с фигурой при её перемещении`
При переходе в режим вращения фигуры и её перемещении в LibreOffice Impress или Draw можно увидеть, что центр фигуры остаётся на том месте, где был центр фигуры до перемещения. При этом фигура вращается по оси, заданной центром до перемещения. <br>
<p align="center">
  <img src="https://sun9-64.userapi.com/impg/ePNuKRTFVuX5Zodc3c5J11XLMuJqAitgqBtBKQ/7BnArYXQhA0.jpg?size=567x797&quality=96&sign=f34b6d487b7778f3455c44766b801ff4&type=album" width="350" height="500">
  <img src="https://sun9-50.userapi.com/impg/lkO0WAVGZJTLdtkYfAm8T_WYo1bU4AQdJsFeCQ/iZZtvvAv7-I.jpg?size=564x800&quality=96&sign=e15eba050f59336e50d850a187440097&type=album" width="350" height="500">
</p><br>
## `BUG №3 - Летающий текст в текстовом поле`
При создании текстового поля и заполнении его текстом, можно добавить рамку. Изначально стиль линии у текстового поля стоит "none", но если поменять толщину линии, а затем поставить её тип, то текст будет выходить за рамку, либо рамка будет на него наезжать (в зависимости от толщины линии). <br>
<p align="center">
  <img src="https://sun9-88.userapi.com/impg/VD4soqGR5xgsZPFawj2izFgVuhkt1CqXKvluIg/xnStxxbIvfY.jpg?size=1366x768&quality=96&sign=838f6d2ae350eb2d0e702bcd8fcfb877&type=album">
  <img src="https://sun9-9.userapi.com/impg/Y70U_An1QfQai3LFhKyjx4fnyzW7SYa8L1lsZg/-2PkUEAD4L0.jpg?size=451x523&quality=96&sign=c6f1d78e74f330937bdbdaa7dfe0d9ad&type=album">
  <img src="https://sun9-36.userapi.com/impg/i02Yqye7jt1NFBP1hqwQRYSl3Ul1JXAtCW4_eQ/FtV1FkFrksA.jpg?size=1366x768&quality=96&sign=5967e6625b794c35b3dcfe3f6744216f&type=album">
  <img src="https://sun9-85.userapi.com/impg/aM4ZSej0VLydAZCYOWZgbMgpnXjU9k_NTD4YIQ/RQa_AQDLz8s.jpg?size=1366x768&quality=96&sign=8e819adf66ab171f7bc026cde80ade77&type=album">
 </p><br>
