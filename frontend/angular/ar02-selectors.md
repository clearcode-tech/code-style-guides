## Angular Rule: Selector'ы в Angular проекте



Правила создания selector'ов в Angular проекте.

1. Для группы selector'ов создаётся ts файл some.selectors.ts в папке store/selectors.

2. Создаём selector всего состояния с помощью фабричной функции createFeatureSelector.
   Хоть имя состояния и SomeState, но селектор - state, а не someState. Это необходимо, чтобы не было дублирования имени при использовании селектора через экспортируемый объект, объединяющий селекторы.

   ```
   /**
    * Селектор состояния ...
    */
   const state = createFeatureSelector<SomeState>("someState");
   ```

3. Создаём selector'ы необходимых сущностей с помощью фабричной функции createSelector, в качестве параметра которой передаётся селектор, созданный на предыдущем шаге, вместе с модифицирующей состояние лямбдой.

   ```
   /**
    * Селектор ...
    */
   const entity = createSelector(
       state,
       (state: SomeState): SomeEntity => state.entity
   );
   ```

4. В конце файла создаём и экспортируем объект-контейнер, который содержит в себе все selector'ы.

   ```
   /**
    * Объект, объединяющий селекторы ...
    */
   export const SomeStateSelectors = {
   	state,
   	entity,
   }
   ```