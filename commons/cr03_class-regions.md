## Common Rule: Оформление регионов

1. Всегда использовать регионы для разграничения логики в классе.
2. Состав и порядок основных регионов определён ниже.
3. Между основными регионами пустой строки нет.
4. Внутри основных регионов могут быть вложенные регионы. Так, например, регион `Migrations` вложен в регион `Public` в примере ниже.
5. Вложенные регионы обособляются пустой строкой от внешнего сверху и/или снизу. Между идущими подряд вложенными регионами пустой строки нет.

Состав и порядок основных регионов для Java:

- `Constants` - Константы класса. При большом количестве констант регион можно разбить на `Public constants`, `Protected constants` и `Private constants`.
- `Fields` - Поля класса. При большом количестве полей регион можно разбить на `Public fields`, `Protected field` и `Private fields`.
- `Ctor` - Конструкторы класса.
- `Static factories` - Статические фабричные методы.
- `Public static` - Публичные статические методы класса.
- `Public` - Публичные методы экземпляра класса.
- `Protected static` - Защищённые статические методы класса.
- `Protected` - Защищённые методы экземпляра класса.
- `Private static` - Приватные статические методы класса.
- `Private` - Приватные методы экземпляра класса.

Состав и порядок основных регионов для TypeScript:

- `Constants` - Константы класса. При большом количестве констант регион можно разбить на `Public constants`, `Protected constants` и `Private constants`.
- `Inputs` - Входящие данные "тупого" Angular компонента.
- `Outputs` - Исходящие события "тупого" Angular компонента.
- `Fields` - Поля класса. При большом количестве полей регион можно разбить на `Public fields`, `Protected field` и `Private fields`.
- `Ctor` - Конструкторы класса.
- `Hooks` - Методы Angular-компонента, представляющие его этапы жизненного цикла.
- `Getters and Setters` - `get` и `set` методы TypeScript'а.
- `Public static` - Публичные статические методы класса.
- `Public` - Публичные методы экземпляра класса.
- `Events` - Обработчики событий.
- `Protected static` - Защищённые статические методы класса.
- `Protected` - Защищённые методы экземпляра класса.
- `Private static` - Приватные статические методы класса.
- `Private` - Приватные методы экземпляра класса.

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
     *
     * @return ...
     */ 
    public List<String> getMigrationLocations() {

        return ...;
    }

    //endregion

    //endregion
}
```

Для Typescript аналогично.
