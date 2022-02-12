---
# Front matter
title: "Отчет по лабораторной работе №1"  
subtitle: "Использование git"  
author: "Ильин Никита Евгеньевич"  
group: "NFIbd-01-19"    
institute: "RUDN University"  
date: "2022 Feb 10th"  

# Generic otions
lang: ru-RU
toc-title: "Содержание"

# Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

# Pdf output format
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
### Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Misc options
indent: true
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Цель данной работы --- Изучение основ работы с системой контроля версий git.

# Задание
| Номер задачи | Описание задачи                                                                                                          |
|--------------|----------------------------------------------------------------------------------------------------------------------------|
|1.1| Подготовка к работе с git.|
|1.2| Создание проекта.|
|1.3| Внесение изменений в файлы.|
|1.4| Индексация изменений.|
|1.5| Отмена локльных изменений (до индексации).|
|1.6| Отмена проиндексированных изменений.|
|1.7| Отмена коммитов.|
|1.8| Удаление коммитов из ветки.|
|1.9| Удаление тега oops.|
|1.10| Внесение изменений в коммиты.|
|1.11| Перемещение файлов.|
|1.12| Второй способо перемещения файлов.|
|1.13| Подробнее о структуре.|
|1.14| Git внутри: Каталог .git.|
|1.15| Работа непосредственно с объектами git.|
|1.16| Создание ветки.|
|1.17| Навигация по веткам.|
|1.18| Изменения в ветке master.|
|1.19| Сделайте коммит изменений README.md в ветку master.|
|1.20| Слияние.|
|1.21| Создание конфликта.|
|1.22| Разрешение конфликтов.|
|1.23| Сброс ветки style.|
|1.24| Сброс ветки master.|
|1.25| Перебазирование.|
|1.26| Слияние в ветку master.|
|1.27| Клонирование репозиториев.|
|1.28| Просмотр клонированного репозитория.|
|1.29| Что такое origin?|
|1.30| Удаленные ветки.|
|1.31| Изменение оригинального репозитория.|
|1.32| Слияние извлеченных изменений.|
|1.33| Добавление ветки наблюдения.|
|1.34| Чистые репозитории.|
|1.35| Создайте чистый репозиторий.|
|1.36| Добавление удаленного репозитория.|
|1.37| Отправка изменений.|
|1.38| Извлечение общих изменений.|

# Теоретическое введение

| Имя каталога | Описание каталога                                                                                                          |
|--------------|----------------------------------------------------------------------------------------------------------------------------|
| `/`          | Корневая директория, содержащая всю файловую                                                                               |
| `/bin `      | Основные системные утилиты, необходимые как в однопользовательском режиме, так и при обычной работе всем пользователям     |
| `/etc`       | Общесистемные конфигурационные файлы и файлы конфигурации установленных программ                                           |
| `/home`      | Содержит домашние директории пользователей, которые, в свою очередь, содержат персональные настройки и данные пользователя |
| `/media`     | Точки монтирования для сменных носителей                                                                                   |
| `/root`      | Домашняя директория пользователя  `root`                                                                                   |
| `/tmp`       | Временные файлы                                                                                                            |
| `/usr`       | Вторичная иерархия для данных пользователя                                                                                 |

# Выполнение лабораторной работы

1. Указываем имя и электронную почту для git  
![рис. 1](images/image001.png)
2. Устанавливаем параметры установки окончаний строк  
![рис. 2](images/image002.png)
3. Устанавливаем отображение unicode  
![рис. 3](images/image003.png)
4. Создаем страницу Hello World  
![рис. 4](images/image004.png)  
5. Создаем репозиторий  
![рис. 5](images/image005.png)  
6. Добавление файла в репозиторий  
![рис. 6](images/image006.png)
7. Проверяем состояние репозитория  
![рис. 7](images/image007.png)
8. Изменяем страницу Hello World  
![рис. 8](images/image008.png)
9. Индексируем изменения  
![рис. 10](images/image010.png)
10. Коммит изменений  
![рис. 10](images/image011.png)  
![рис. 11](images/image012.png)
11. Добавляем стандартные теги страницы  
![рис. 12](images/image013.png)  
![рис. 13](images/image014.png)  
![рис. 14](images/image015.png)  
![рис. 15](images/image016.png)  
![рис. 16](images/image017.png)  
12. История изменений  
![рис. 17](images/image018.png)  
![рис. 18](images/image019.png)  
13. Получение старых версий  
![рис. 19](images/image020.png)  
![рис. 20](images/image021.png)  
14. Создание тегов версий  
![рис. 21](images/image022.png)  
![рис. 22](images/image023.png)  
![рис. 23](images/image024.png)  
![рис. 24](images/image025.png)  
15. Переключение по имени тега  
![рис. 25](images/image026.png)  
![рис. 26](images/image027.png)  
16. Просмотр тегов с помощью команды tag  
![рис. 27](images/image028.png)  
17. Переключаемся на ветку master  
18. Изменяем файл hello.html  
19. Проверяем состояние  
![рис. 28](images/image029.png)  
20. Отменяем изменения в рабочем каталоге  
![рис. 29](images/image030.png)  
21. Измененяем файл и индексируем изменения  
![рис. 30](images/image031.png)  
22. Проверьте состояние  
![рис. 31](images/image032.png)  
23. Выполняем сброс буферной зоны  
![рис. 32](images/image033.png)  
24. Переключаемся на версию коммита  
![рис. 33](images/image034.png)  
25. Отменяем коммит  
![рис. 34](images/image035.png)
26. Изменяем файл и делаем коммит  
![рис. 35](images/image036.png)
27. Делаем коммит с новыми изменениями, отменяя предыдущие  
![рис. 36](images/image037.png)
28. Проверяем лог  
![рис. 37](images/image038.png)
29. Выполняем команду git reset  
30. Проверяем историю  
![рис. 38](images/image039.png)
31. Отмечаем ветку  
![рис. 39](images/image040.png)
32. Делаем сброс коммитов к предшествующим коммиту Oops  
![рис. 40](images/image041.png)
33. Удаление тега Oops  
![рис. 41](images/image042.png)
34. Изменяеем страницу и делаем коммит  
![рис. 42](images/image043.png)
35. Изменяем предыдущий коммит  
![рис. 43](images/image044.png)
36. Перемещаем файл hello.html в каталог lib  
![рис. 44](images/image045.png)
37. Делаем коммит в новый каталог  
![рис. 45](images/image046.png)
38. Добавляем файл Index.html  
![рис. 50](images/image050.png)
![рис. 51](images/image051.png)
39. Каталог .git  
![рис. 48](images/image052.png)
40. Углубляемся в базу данных объектов  
![рис. 49](images/image053.png)
41. Открываем Config файл  
![рис. 57](images/image057.png)
42. Ветки и теги  
![рис. 58](images/image058.png)
43. Открываем файл HEAD  
![рис. 59](images/image059.png)
44. Поиск последнего коммита  
![рис. 60](images/image060.png)
45. Вывод коммита с помощью SHA1 хэша  
![рис. 61](images/image061.png)
46. Поиск дерева  
![рис. 62](images/image062.png)
47. Вывод каталога lib  
![рис. 63](images/image063.png)
48. Вывод файла hello.html  
![рис. 64](images/image064.png)
49. Создаем ветку  
![рис. 65](images/image065.png)
50. Добавляем файл стилей style.css  
![рис. 66](images/image066.png)
51. Изменяем файл index.html  
![рис. 67](images/image067.png)
52. Переключаемся на ветку master  
![рис. 69](images/image070.png)
53. Возвращаемся к ветке style  
![рис. 70](images/image071.png)
54. Создаем файл README в ветке master  
![рис. 71](images/image072.png)
55. Делаем коммит изменений  
![рис. 73](images/image073.png)
56. Просматриваем текущие ветки  
![рис. 74](images/image074.png)
57. Выполняем слияние веток  
![рис. 75](images/image075.png)
58. Создаем конфликт  
![рис. 76](images/image076.png)
59. Выполняем слияние веток master и style, и решаем конфликт  
![рис. 77](images/image077.png)
60. Делаем коммит решения конфликта  
![рис. 78](images/image078.png)
61. Сброс ветки style. Проверяем ветку  
![рис. 79](images/image079.png)
62. Сброс ветки master  
![рис. 80](images/image080.png)
63. Перебазирование  
![рис. 81](images/image081.png)
64. Слияние style в master  
![рис. 82](images/image082.png)
65. Изменяем оригинальный репозиторий  
![рис. 92](images/image092.png)
66. Проверяем README  
![рис. 93](images/image094.png)
67. Сливаем извлеченные изменения  
![рис. 94](images/image095.png)
68. Добавляем локальную ветку, отслеживающую оригинальную  
![рис. 96](images/image096.png)
69. Отправляем изменения  
![рис. 99](images/image099.png)
![рис. 100](images/image100.png)
70. Извлекаем общие изменения  
![рис. 101](images/image102.png)


# Выводы

В ходе данной работы были получены навыки использования системы контроля версий git. А также работы с сервисом GitHub.

