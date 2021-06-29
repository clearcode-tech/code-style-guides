## Angular Rule 04: CSS, SMACSS, Stylelint

### SMACSS (Scalable and Modular Architecture for CSS)
Это набор правил code style для CSS. Описывает именование, форматирование, порядок свойств.

Источник:
http://smacss.com/

Перевод:
https://medium.com/@companjero/e601222cd4eb


### Stylelint
Это линтер для CSS и SCSS. Начиная с задачи HRL-296 он входит в список пакетов для установки в модуле **ekd-ui**.
Как его настроить для использования:

0. Перейти в папку модуля **ekd-ui**

1. Чтобы установились нужные пакеты:
`yarn install`

2. В IDEA открыть настройки: File | Settings | Languages & Frameworks | Style Sheets | Stylelint

    - Поставить галочку (enable)

    - Stylelint package:
    `<path-to-ekd-ui>/node_modules/stylelint`

    - Configuration file:
    `<path-to-ekd-ui>/stylelint_config.js`
