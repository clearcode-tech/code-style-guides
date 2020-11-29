## Common Rule: Количество return в методе 



1. Беспроигрышный вариант - использовать только 1 return в методе. Но следующие пункты могут облегчить рефакторинг и улучшить качество кода.

2. Использовать более одного return в методе разрешено, когда потенциальный return является исключительной ситуацией.

   Пример №1. В данном случае разрешено использовать `return 0`  и `return 1`, так как они являются исключениями из общего случая.

   ```
   /**
    * <p>Возвращает число Фибоначчи.</p>
    * 
    * @param n Номер числа Фибоначчи.
    * 
    * @return Число Фибоначчи.
    */  
   private int fibonacci(int n) {
   
       if (n <= 0) {
   
           return 0;
       }
   
       if (n == 1) {
   
           return 1;
       }
   
       return fibonacci(n - 1) + fibonacci(n - 2);
   }
   ```

3. Если метод заканчивается на if-else, то return можно использовать внутри каждой ветки. 

   Пример №2.

   ```
   /**
    * <p>Возвращает звук животного.</p>
    * 
    * @param animal Животное.
    * 
    * @return Звук животного.
    */ 
   private String getAnimalSound(Animal animal) {
   
       this.someCounter = this.someCounter + 1;
   
       if (animal == Animal.DOG) {
   
           return "woof";
       }
       else {
   
           return "meow";
       }
   }
   ```