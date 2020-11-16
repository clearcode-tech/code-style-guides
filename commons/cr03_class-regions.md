## Common Rule: Оформление регионов



1. Всегда использовать регионы для разграничения логики в классе.
2. Регионы могут быть вложены друг в друга. Так, например, регион Migrations вложен в Public в примере ниже.
3. Вложенные регионы обособляются пустой строкой от внешнего.
4. Между регионами пустой строки нет.

Последовательность регионов:

- Constants - константы класса
- Inputs - входящие данные “тупого” Angular компонента
- Outputs - исходящие данные “тупого” Angular компонента
- Fields - поля класса. При большом их количестве можно разбить на Public Fields и Private Fields
- Ctor - конструкторы класса
- Static factories - статические методы фабрики
- Hooks - методы Angular компонента, представляющие его этапы жизненного цикла
- Getters and Setters - get и set методы TypeScript'а
- Public - публичные методы
- Events - обработчики событий
- Private - приватные методы

Пример для Java:

```
/**
 * <p>...</p>
 */
public final class ClassName {
    //region Constants

    /**
    * <p>...</p>
    */
    private static final String STRING_CONSTANT = "string constant value";

    //endregion
    //region Ctor

    /**
    * <p>Конструктор класса ...</p>
    */
    @Inject
    public ClassName() { }

    //endregion
    //region Public

    //region Migrations

    /**
    * <p>Возвращает ...</p>
    */ 
    public List<String> getMigrationLocations() {

    	return ...;
    }

    //endregion

	//endregion
}
```

Для Typescript аналогично.