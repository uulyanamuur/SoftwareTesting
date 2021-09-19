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
LibreOffice Writer предоставляет функцию рисования линии в документе, цвет которой по умолчанию синий. Если же попробовать изменить цвет уже нарисованной линии на любой другой (в данном случае был выбран оранжевый), то ничего не поменяется, и линия останется того же синего цвета по умолчанию. Аналогичная ситуация и с выбором цвета заранее и рисованием линии.
![bug1](https://sun9-63.userapi.com/impg/vlvaZtF4SNrI311nnEDxXA_tzEGQZYqHD5TqYg/XE1zEGir-dk.jpg?size=1920x1080&quality=96&sign=6a2687be6e6f9a878fabe22c55edd91c&type=album)
