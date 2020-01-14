# Задание 2.


## План работ

https://github.com/appalse/shri-2/blob/master/README-Plan.md


## Структура папок

| Папка | Описание |
| ----- | -------- |
| .\build\ | бандл с результатами сборки |
| .\mochawesome-report\ | результаты автотестов, **mochawesome.html** открывается локально и отображает последний прогон |
| .\src\   | исходный код        |
| .\test\  | тесты на mocha+chai |


## Сборка и тесты

Собрать bundle в .\build\linter.js:
```
npm run build
```

Запустить тесты:
```
mocha --reporter mochawesome
```

Результаты тестов лежат в .\mochawesome-report\mochawesome.html


## Комментарии по выбору инструментов

### Среда разработки - Visual Studio Code

Пользуюсь Visiaul Studio Code, потому что она free, удобная, не зависает и быстро запускается, быстро работает, есть плагины, которые ускоряют работу, встроенный терминал. Во многих примерах, на курсах используется он. В целом, нравится.

### Пакетный менеджер - npm

Нет опыта, после прочтения статей стоял выбор между npm и yarn. Выбран npm, потому что :
* на hh.ru в вакансиях в два раза больше упоминаний npm, чем yarn. 
* npm является дефолтным пакетным менеджером Node.js и у него большое сообщество. Быстрее и легче найти ответы на вопросы. 
* достаточно быстрый, не сильно уступает yarn. 

### Тестовый фреймворк - mocha + chai

Нет опыта. После прочтения статей выделены Jasmine и mocha + chai. Выбрано второе, потому что : 
* нет лишнего, библиотека ассертов отдельно -> модульно. 
* более популярно, количество использований в репозиториях ~ сотни тысяч. Часто требуется в вакансиях на hh.ru
* мне понравился синтаксис проверок в chai (через точки, should/assert/expect).

### Сборщик - webpack

Нет опыта. После прочтения статей выделены webpack и gulp. Так как webpack более популярен, в 2 раза чаще упоминается в вакансиях на hh.ru, то выбор остановился на нем.

### Плагины и утилиты

* **Babel** (babel-loader, @babel/core, @babel/preset-env) - для транспилирования Javascript (2015+, ES6+) в код, поддерживаемый браузерами, в т.ч. старыми, так как в задании сказано, что линтер должен работать в разных браузерах. Выбран, потому что часто встречается в вакансиях на hh.

* **ESLint** (eslint cli) - для проверки кода, codestyle. Выбран, потому что часто встречается в вакансиях на hh.

* **eslint-detailed-reporter** - для генерации отчета ESLint. Удобный и понятный внешний вид, были скриншоты в описании. 

* **clean-webpack-plugin** - плагин webpack, который чистит папку с результатами сборки. Упоминался в документации к webpack, поэтому взят оттуда.

* Для генерации бандла, который можно запустить в html и в node.js, применено решение [отсюда](https://stackoverflow.com/questions/49111086/webpack-4-universal-library-target).

* **mochawesome** - модуль для генерации отчета о тестировании. Выбирала по скриншотам, у mochawesome самые удобные и понятны отчеты. 


## Комментарии по реализации

### Парсер входных данных

Выбран json-to-ast, потому что его упоминали в Issues, в нем уже есть location объектов, понятная структура.  

### Алгоритм

Рекурсивно обходим синтаксическое дерево, полученное после парсинга библиотекой json-to-ast. При входе в узел сохраняем родителей, при выходе восстанавливаем их. Если встречаются блоки warning, heading, grid, то добавляем значимую информацию в объект с родителями (Parents), идем дальше в глубину. Одновременно делаем проверки блоков в отдельных функциях <check*>, которые находятся в отдельных папках в отдельных файлах.

### Методология разработки

TDD и итеративный подход. Сначала были написаны тесты по одному правилу, затем правило реализовано, тесты и код отлажены. Затем тесты следующего правила, код следующего правила и т.д. После реализации всех правил одного блока делался рефакторинг. 

