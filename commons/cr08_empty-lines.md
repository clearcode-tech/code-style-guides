## Common Rule 8: Пустые строки

1. Блоки кода с разной семантикой разделяются пустой строкой.
   ```       
   /**
    * ...
    *
    * @return ...
    */
    public String SomeMethod(another) {
       ...
   
       var person1 = this.call(...);
       var person2 = this.call(...);
       var person3 = this.call(...);
       var person4 = this.call(...);
       
       var document1 = this.call(...);
       var document2 = this.call(...);
       var document3 = this.call(...);
       var document4 = this.call(...);
   
       ...
   }
   ```
2. После однострочной сигнатуры метода всегда ставится пустая строка.
   ```
   /**
    * ...
    *
    * @return ...
    */
    public String SomeMethod(another) {
        
        this.call();
        ...
   }
3. Перед блоком кода в if/else всегда ставится пустая строка.
    ```
   /**
    * ...
    *
    * @return ...
    */
    public void SomeMethod(another) {
   
       if (condition1) {
   
         doSomething1();
       }
       else (condition2) {
   
         doSomething2();
       }
    }
    ```
4. Перед return всегда добавляется пустая строка.
    ```
    /**
    * ...
    *
    * @return ...
    */
    public String SomeMethod(another) {
      
       String some2 = this.asdAsadasdasdAsdasdasdas(some1)
         .filter(...)
         .findAny()
         .orElseThrow();
        
       return another + some2;
    }
    ```
    ```
    /**
    * ...
    *
    * @return ...
    */
    public String SomeMethod(another) {
          
       String some1 = "asdAsadasdasdAsdasdasdas";
       int some2 = 3426482354763425763466876;
       
       return some1 + somt2;
    }
     ```
   Исключение: в методе есть одно однострочное объявление переменной, которая в следующей строке 
   используется в return.
    ```       
   /**
    * ...
    *
    * @return ...
    */
    public String SomeMethod(another) {
        
        LongClassName some = this.service.callLongName(another);
        return another + some;
    }
   ```
  