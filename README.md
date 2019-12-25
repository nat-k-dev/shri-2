# Задание 2.

## План

### Подготовка

* ~~написать заглушку основной функции, на вход строка, на входе пустой массив~~
* ~~выбрать фреймворк для тестов.~~ 
* ~~Изучить выбранный тестовый фреймворк.~~
* ~~написать тест на проверку пустого массива при пустых входных данных~~
* ~~прочитать про webpack, запустить демо пример. Сравнить его с другими сборщиками, написать про выбранный сборщик в readme.md~~
* ~~понять как использовать собранную функцию. lint is not a function~~
* ~~прочитать про browserify (чтобы запустить в браузере, если с webpack не получится).~~
* ~~понять как все это запускать - функцию и тесты. Проверить на NodeJS и в браузере~~

### Прототип

* написать тесты.
* придумать архитектуру, разделить задание на блоки, компоненты. Создать папки для кусков кода.
* создать файлы с функциями заглушками под каждый компонент. Запустить сборщик, из каждой функции выводить что-то в консоль. Проверить в node.js и в браузере.
* выделить функциональность, которую можно взять из готовых библиотек.

### Реализация

* реализовать правила по одному. Для некоторых функций искать готовые библиотеки, которые можно встроить без лишних зависимостей и менее 1 Мб. Обосновать в readme.
* дописать readme.
* оптимизация кода, рефакторинг, ревью кода.
* проверить оформление кода, комментарии, если нужны, имена переменных.


## Комментарии по выбору инструментов

### Пакетный менеджер - npm

В статьях по программированию, которые я читала, использовались npm или yarn. Поэтому было решено изучить обзоры и сравнения этих двух пакетных менеджеров 2019 года. По результатах сравнения выбрала npm, потому что
1. Он является дефолтным пакетным менеджером Node.js и у него большое сообщество. Значит баги фиксятся и есть возможность найти готовые решения и ответы на вопросы. 
2. Раньше yarn был в 2 раза быстрее и имел возможность записывать версии в lock файл. Так как сейчас npm стал достаточно быстрый и тоже имеет lock файл, то разницы в этому пункте нет.
3. В одной [статей](https://medium.com/@vincentnewkirk/npm-vs-yarn-2019-e88757b17038) рассказывалось об ошибке версий yarn, которая была исправлена после перехода на npm. Хотя сама статья толком не объяснила причины, но так как ресурс medium обычно содержит полезные статьи, то кредит доверия к статье высокий. Поверила автору.
4. На hh.ru в вакансиях в два раза больше упоминаний npm, чем yarn. Смогу добавить пункт в свое резюме и сделать его привлекательнее. 
5. Во многих статьях указывали, что yarn более безопасен (он для того и создавался, чтобы быть безопасным пакетным менеджером), в то время как npm в одно время содержал дыры в безопасности (module hijacking). Но предыдущий пункт перевешивает этот недостаток. Возможно, я мало изучила этот вопрос, ведь не с проста так много компаний на hh.ru указывают npm в вакансиях.

### Тестовый фреймворк - mocha + chai

У меня нет опыта работы с тестовыми фреймворками javascript. Были изучены несколько статей-обзоров на тестирование javascript в 2019 году. Затем выделены пара наиболее рекомендуемых фреймворков:
* Jasmine
* Mocha + chai

Были выбраны mocha + chai, потому что
1. Хотя в Jasmine есть все необходимые библиотеки, в том числе библиотека ассертов, можно было бы использовать только ее одну. Но, скорее всего, в ней есть что-то лишнее. Поэтому будет больше занимать места на диске и, возможно, дольше собираться.
2. В github репозиториях у mocha и chai сотни тысяч использований. А у Jasmin около пяти тысяч. Значит mocha и chai более популярные. Полезно освоить то, что популярно, т.к. наиболее вероятно это встретить еще где-то после выполнения задания. 
3. В вакансиях frontend разработчиков часто требуется знание mocha и chai. Можно будет добавить в свое резюме после изучения.
4. Синтаксис проверок chai больше понравился, то, что проверки через точки, и что есть 3 варианта задания: should, assert, expect.

### Сборщик - webpack

Я слышала про webpack и gulp. Так как webpack более популярен, в 2 раза чаще упоминается в вакансиях на hh.ru, то сразу выбрала его.

### Среда разработки - Visual Studio Code

Пользуюсь Visiaul Studio Code, потому что бесплатный, удобный, не зависает и быстро запускается, быстро работает, есть плагины, которые ускоряют работу, встроенный терминал. Во многих примерах, на курсах используется он. Мне нравится, другие решения не искала, так как эта среда нравится.
