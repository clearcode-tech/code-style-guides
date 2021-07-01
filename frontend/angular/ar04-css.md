## Angular Rule 04: Порядок свойств CSS

Для определения порядка свойств мы пользуемся рекомендациями SMACSS (Scalable and Modular Architecture for CSS), которые устанавливают порядок категорий:
1. Box
2. Border
3. Background
4. Text
5. Other

Источник: http://smacss.com/book/formatting#grouping

Полный порядок свойств: https://github.com/cahamilton/css-property-sort-order-smacss/blob/master/index.js

Для поддержки этого правила в проекте должен быть настроен линтер, который подскажет, если порядок был нарушен.

### Настройка Stylelint в UI-проекте

1. Установить stylelint:
    ```
    npm install --save-dev stylelint
    ```
2. Установить конфигурацию, либо можно использовать готовый файл:
    ```
    npm install --save-dev stylelint-config-standard
    ```
3. Установить stylelint-order:
    ```
    npm install --save-dev stylelint-order
    ```
4. Установить stylelint-config-property-sort-order-smacss:
    ```
    npm install --save-dev stylelint-config-property-sort-order-smacss
    ```
5. Перенести файл конфигурации из `<project>/node_modules/stylelint-config-recommended/index.js` в `<project>/stylelint_config.js`. После этого пакет `stylelint-config-standard` можно удалять.

6. Добавить в файл конфигурации перед нодой 'rules':
    ```
    'plugins': [
        'stylelint-order'
    ],
    'extends': 'stylelint-config-property-sort-order-smacss',
    ```
7. В IDEA открыть настройки: File | Settings | Languages & Frameworks | Style Sheets | Stylelint

    - Поставить галочку (enable)

    - Stylelint package:
    `<project>/node_modules/stylelint`

    - Configuration file:
    `<project>/stylelint_config.js`
