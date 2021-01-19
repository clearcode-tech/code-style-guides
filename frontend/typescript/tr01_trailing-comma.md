## Typescript Rule: Trailing commas

Trailing commas("висящие/замыкающие/завершающие/последние запятые") используются для последнего элемента в многострочном перечислении.
1. Перечисление элементов массива.
    ```
    const array: number[] = [
        1,
        2,
        3,
    ];
    ```
2. Перечисление полей при создании объекта.
    ```
    const object: PersonWithName = {
        name: "qwerty",
        version: 1,
    };
    ```
3. Параметры методов.
   ```
   someMethod(
        firstArgument,
        secondArgument,
        thirdArgument,  
   ): void { }
   ```
4. Аргументы, передаваемые в метод.
    ```
    someMethod2(): void {
    
        this.someMethod(
            firstArgument,
            secondArgument,
            thirdArgument,  
        );
    }
    ```
Использовать такие запятые не нужно, если перечисление происходит в одну строку:
```
const array = [ 1, 2, 3 ];
const object = { name: "qwerty", version: 1 };
```
   
#### Для чего нужны trailing commas: 
- При добавлении ещё одной строки к перечислению коммит будет задевать только одну строку, что является более наглядным вариантом.
- Все элементы в перечислении выглядят одинаково.
- Удобнее менять порядок элементов перечисления (вырезать строку и вставить из любой позиции в любую).   

#### Настройки для TSLint: 
Для TSLint правила для trailing commas отсутствуют по умолчанию. Для задания правил достаточно добавить правило в файл настроек TSLint: 
```
"trailing-comma": [true, {"multiline": "always", "singleline": "never"}]
```
