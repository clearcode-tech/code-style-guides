## Angular Rule: Импорты в Angular



Правила для указания импортов в Angular исходят из основных мыслей:

- не должна требоваться ручная сортировка/форматирование импортов
- единообразие всех импортов
- алфавитный порядок внутри групп импортов
- допускается, чтобы импорт был длиннее, чем ограничение на длину строки в коде

В связи с этим применяются следующие правила:

- Импорт одного класса/интерфейса/значения в одной строке в отдельном импорте. Т.е. группировка нескольких элементов в один импорт не используется.
- Полный путь импорта от корня проекта вплоть до конкретного файла. Это поможет навсегда избавиться от возможных циклических зависимостей, когда путь импорта идёт лишь до папки, в которой есть index.ts. Это в свою очередь приводит к тому, что нет нужды вести index.ts, будем от них потихоньку избавляться.
- Импорты автоматически группируются и сортируются средствами IDE.

Чтобы всего этого достичь в IDEA нужно указать следующие настройки для импортов в TypeScript (нужно **все** настройки привести в соответствие со скриншотом):

![settings](/images/frontend/angular/imports/1.png)

Также для единого форматирования импортов нужно указать дополнительные настройки для TypeScript:

![settings](/images/frontend/angular/imports/2.png)

![settings](/images/frontend/angular/imports/3.png)

Допустимость длинных строк импортов, выходящих за максимальную длину строки, контролирует правило TSLint:

```
"max-line-length": [
    true,
    {
        "limit": 120,
        "ignore-pattern": "^import|^export"
    }
]
```

Пример оформленных в соответствие с этими правилами импортов:

![settings](/images/frontend/angular/imports/4.png)



###### Рефакторинг импортов, оформленных без применения этих правил

Если при работе над задачей вы понимаете, что вы будете изменять файл, в котором импорты оформлены не по этим правилам, то приветствуется выполнить рефакторинг оформления импортов. Сделать это следует отдельной операцией, чтобы изменения оформления не были в одном коммите с логическими изменениями. Проще всего сразу выполнить рефакторинг оформления импортов, сделать коммит с этими изменениями, после чего внести логические изменения, которые требует задача.

При рефакторинге оформления импортов чаще всего нужно будет выполнить:

- использование двойных кавычек вместо одинарных
- избавление от относительных путей
- указание путей вплоть до файла
- избавление от сгруппированных импортов
- удаление пустых строк, которые разбивают импорты на группы

После чего можно нажать Ctrl + Alt + O, чтобы IDEA автоматически отсортировала импорты.