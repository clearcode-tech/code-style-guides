## Common Rule: Порядок полей класса при объявлении и в конструкторе



При перечислении полей в классе, их порядок должен сохраняться и в конструкторе. Это вносит определённый порядок, уменьшает хаос в коде.

В случае с наследование первыми идут поля, которые объявлены в базовом/-ых классах.

Например, для Java это даже IDEA поддерживает. Добавили поле класса, нажали Alt + Enter на нём, и IDEA предложит добавить это поле как входной параметр конструктора. И если сделать эту операцию, то IDEA добавит параметр в конструктор согласно порядку полей при объявлении. 

Java:

```
@Singleton
public class SomeService {
    //region Fields
    
    /**
     * ...
     */
    private final DateParser dateParser;
    
    /**
     * ...
     */
    private final SomeExtractor someExtractor;
    
    //endregion
    //region Ctor
    
    /**
     * ...
     *
     * @param dateParser ...
     * @param someExtractor ...
     */
    @Inject
    public SomeService(DateParser dateParser, SomeExtractor someExtractor) {
    
        this.dateParser = dateParser;
        this.someExtractor = someExtractor;
    }
    
    //endregion
}
```

Typescript:

```
@Injectable({
    providedIn: "root"
})
public class SomeService {
    //region Fields
    
    /**
     * ...
     */
    private readonly DateParser _dateParser;
    
    /**
     * ...
     */
    private readonly SomeExtractor _someExtractor;
    
    //endregion
    //region Ctor
    
    /**
     * ...
     *
     * @param dateParser ...
     * @param someExtractor ...
     */
    constructor(DateParser dateParser, SomeExtractor someExtractor) {
    
        this._dateParser = dateParser;
        this._someExtractor = someExtractor;
    }
    
    //endregion
}
```



TODO: Пример с наследованием

