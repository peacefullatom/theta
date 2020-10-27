# [Module 1. Angular introduction. Angular-cli.](../module-1/index.md) (Aleksandr Linkov)

Рассмотреть базовые команды при создании проекта через _angular-cli_.

Особенно _ng new_, _generate_, _build_, _test_
В рамках _ng new_ обратить внимание на _viewencapsulation_, _style_, _routing_.

Создать проект с препроцессором, роутингом и тестами.
Изучить структуру проекта. Изучить файлы _tsconfig_, _tslint_, _angular.json_.

Запустить проект.

Собрать проект с флагом prod. Посмотреть на результат (два бандла).

Создать свой компоненты через ng generate. Изучить структуру файлов внутри одного компонента.

**Задание**: _создать новый проект, подключить ng-bootstrap._

# [Module 2. Components.](../module-2/index.md) (Kirill Sklyarov)

Темплейт синтаксис.

Интерполяция _{{}}_.

Темплейт рефренс _#var_.

Контекст выражений (разница между _attr=_ и _[attr]_).

Обработка событий _(click)_.

Селекторы кастомных компонентов.

Двойное связывание (_banana box_).

Селектор _:host_.

**Задание**: _сверстать главную страницу, header, footer._

# [Module 3. Components interaction.](../module-3/index.md) (Yuriy Markov)

_@Input_, _@Output_ декораторы.

_@ViewChild_, _@ViewChildren_ декоратор.

Content projection: _ng-template_, _ng-content_.

_Pipes_ in templates.

Жизненный цикл компонентов.

**Задание**: _закончить верстку. Добавить получение данных из сервиса. Добавить пайп._

# Module 4. Directives (structural and attributive). (Kostiatyn Kharlap)

Структурные директивы: _\*ngIf_, _\*ngFor_.

Custom structural directive: _viewportSize_.

Attributive directives: _ngClass_.

Custom attributive directives: _hints_, _tooltips_, etc.

**Задание**: _Создать кастомную структурную директиву viewportSize для отображения контента в зависимости от размера экрана и кастомную аттрибутивную директиву для hint’а._

# Module 5. Services. Services and business logic.

_DI_. Сервисы. Как провайдить. (levels of services: global and local).

Difference of providing of service in module and component.
Multi services.

Injection tokens (localStorage, unit-testing).

Common services use-cases: common logic, app state.

**Задание**: _Добавить получение данных из сервиса._

# Module 6. Modules. Router. Project Structure. Lazy-loading.

Как работает _import_, _export_, _declaration_.

Роутер и пути. (только _{path, component}_)

Вложенность _forRoot()_, _forChild()_, _ModuleWithProviders_.

_Lazy-loading_, разбитие на чанки.

Как организовывать проект в модульную систему и зачем. Модули _Core_ и _Shared_, _Library_ (use cases: component module).

**Задание**: _сверстать страницу авторизации, добавить роутер, организовать проект правильно._

# Module 7. Router. Router data. Guards. Auth. Subscriptions.

Гарды.

Получение данных из роутера.

Роутер и пути. _redirectTo_, \*path: \*\*\*

_Router-outlet_, _nested router-outlets_.

_Resolvers_ (use-case: redirect to external link).

Подписки и проблемы с ними. (только _subscribe_ и _unsubscribe_).

**Задание**: _улучшить роутер (защитить пути, добавить редиректы), добавить авторизацию. реализовать breadcrumbs._

# Module 8. RxJS. Subscriptions. Subjects.

What is a stream? What is under the hood?

_pipe()_, _map()_, _tap()_, _takeUntil()_, _merge()_, _debounceTime()_, _distinctUntilChanged()_.

Custom operations for pipes (need a real example, use cases).

```
export const filterNil = <T>() => (
    source: Observable<T>,
): Observable<NonNullable<T>> => source.pipe(
    filter<T, NonNullable<T>>((value: T): value is NonNullable<T> => !isNil(value)),
);
```

_HOO_ (higher-order observables).

Типы _Subjects_ (app state using subject and behavior subjects).

**Задание**: _Написать логику взаимодействия с сервером через RxJS. Реализовать таблицу с пагинацией, фильртрами и сортировкой с помошью RxJS._

#Module 9. HttpClient. Http interceptor. Error handling.

Синтаксис методов _get_, _post_ и т.д. (types for requests).

Error handling - errors are handled on level of component, service only works with requests.

What is an interceptor.

Http interceptor: append JWT tokens, fix headers, add/clean/sanitze params, redirect to error page in case of 5xx error.

Create mocks for development and testing.

_SOLID_.

Service as a state. State handling using subjects.
REST vs RPC.

**Задание**: _Добавить интерсептор и тостер._

# Module 10. Dynamic Components.

Component Resolvers, Factories, Entry Components.

Use-case: modals.

Pass template for body and footer. Show spinners. Multi-level modals.

**Задание**: _Добавить диалоговые окна для создания и редактирования записей._

# Module 11. Forms. Value Accessor.

Reactive and non-reactive forms.

Dirty, pristine, invalid, touched.

Validators, custom validators.

FormArray/FormGroup.

Dynamic nested form with multiple controls.

Forms don’t mutate original data, they work with replica.

Autocomplete – rxjs fromEvent(\$input).

**Задание**: _Добавить формы и реализовать создание и редактирование записей._

~~# Module 11. Value Accessor.
Autocomplete
Задание: Добавить кастомный мультиселект с тегами.~~

# Module 12. Element Ref. Change Detection.

Change detection strategy.

Change detection reference.

Zone.js.

Run outside of Angular.

**Задание**: _Перевести все компоненты на onPush стратегию._

~~Module 13. Directives. I18n.
tbi
Задание:~~

# Module 13. Unit Testing.

Headless tests running. How to get errors in case of CI build.

Tests debugging.

Explain what the coverage is.

Karma, Jasmine.

Testing components with services.

Testing components with activatedRoute.

Testing components with localStorage.

Testing services.

Testing services with subjects.

Plugins in Karma for prettier tests output.

**Задание**: _покрыть тестами службы и компоненты (не менее 70% кода)._

# Module 14. E2E Testing.

Acceptance testing.

User interaction emulation: pointer events, keyboard events, etc.

Project presentation.

**Задание**: _покрыть основные юзер-пассы._
