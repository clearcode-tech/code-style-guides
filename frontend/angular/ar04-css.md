## Angular Rule 04: Порядок свойств CSS

Для определения порядка свойств мы пользуемся рекомендациями SMACSS (Scalable and Modular Architecture for CSS), который устанавливает такой порядок для категорий:
1. Box
2. Border
3. Background
4. Text
5. Other

Источник: http://smacss.com/book/formatting

Полный порядок свойств здесь: https://github.com/cahamilton/css-property-sort-order-smacss/blob/v2.1.3/index.js


### Stylelint
Это линтер для CSS и SCSS. Чтобы его использовать для подсказок о порядке свойств CSS, надо:

1. Установить stylelint:
```
npm install --save-dev stylelint
```
2. Установить конфигурацию, любо можно использовать готовый файл:
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
5. Добавить в файл конфигурации ( `<project>/node_modules/stylelint-config-recommended/index.js` ) перед 'rules':
```
	'plugins': [
		'stylelint-order'
	],
	'extends': 'stylelint-config-property-sort-order-smacss',
```
6. В IDEA открыть настройки: File | Settings | Languages & Frameworks | Style Sheets | Stylelint

    - Поставить галочку (enable)

    - Stylelint package:
    `<project>/node_modules/stylelint`

    - Configuration file:
    `<project>/node_modules/stylelint-config-recommended/index.js`
