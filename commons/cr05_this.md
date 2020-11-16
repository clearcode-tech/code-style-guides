## Common Rule: Указывать this везде



### Правило применимо к Java. В Typescript это необходимость, без которой код не скомпилируется.

Первое соображение в унификации написания кода в независимости от языка. Когда начинаешь писать на Typescript, то постоянно забываешь написать this, т.к. в Java это не является обязательным. Если же привыкаешь писать this и в Java, и в Typescript, т.е. в нашем случае всегда, то переключение между языками происходит незаметно.

Второе соображение в наглядности при проведении Code Review. В IDEA поля и методы класса подсвечиваются особым цветом, и их можно зрительно отличить. Но когда смотришь код в Битбакете, то там нет таких подсветок, и явное указание, что используется поле или метод класса через this, упрощает понимание кода.

Пример Java

```
public class SomeClass {
    //region Fields
    
    /**
     * ...
     */
    private final int value;
    
    //endregion
    //region Ctor
    
    /**
     * ...
     *
     * @param value ...
     */
    public SomeClass(int value) {
    
        this.value = value;
    }
    
    //endregion
    //region Public
    
    /**
     * ...
     *
     * @return ...
     */
    public int someMethod() {
    
        return (this.value * 2);
    }
    
    /**
     * ...
     *
     * @return ...
     */
    public int anotherMethod() {
    
        return (this.someMethod() * 2);
    }
    
    //endregion
}
```