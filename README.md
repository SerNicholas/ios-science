Вопросы на собеседование iOS-разработчика
==

<span style="font-family: 'Lucida Console';">
Вопросов: 0 | Разобрано: 0
</span>

Objective-C, Foundation:
------------------------
- [Что такое `свойство`?](#Что-такое-свойство)
- Объявление свойств c атрибутами: `retain`, `assign`, `nonatomic`, `readonly`, `copy`, `weak`, `strong`, `unsafe_unretained`?
- Как правильно реализовать сетер для свойства с параметром retain?
- Директива `@synthesize`, `@dynamic`, чем отличаются друг от друга?
- В чем разница между `точечной нотацией` и использованием квадратных скобок?
- Есть ли `приватные и защищенные` методы в Objective-C? 
- Вопрос о `циклах в графах владения` (retain cycle)? 
- Почему свойства delegate (предоставляющие доступ к делегату) обычно задаются как `assign`в MRC или `weak в ARC`?
- Как `использовать` self внутри блоков? Приведите пример `retain cycle` в блоке?
- Чем `категория` отличается от `категории продолжения класса` (extension, наименованная категория)?
- Можно ли добавить `ivar` в категорию?
- Когда лучше использовать `категорию`, а когда `наследование`?
- Как имитировать `множественное наследование`?
- Можно ли чтобы разные классы реализовывали один протокол. (ClassA, ClassB и ClassC - реализуют ClassCProtocol)?
- `Формальный и неформальный (informal)` протокол? `Протоколы (protocols)`: основные отличия между c#/java интерфейсами и Objective-C протоколами? Что делать в случае если класс не реализует какой-то метод из протокола?
- Почему нам не следует вызывать `instance методы в методе -init (initialize)`?
- Что такое `назначенный инициализатор (designated initializer)`? Приведите пример назначенного инициализатора (имеется ввиду `if (self  = [super ...])`)?
- Что происходит когода мы пытаемся вызвать метод у nil указателя? Разница между nil и Nil и [NSNull null]?
- Что такое `селектор (selector)`? Как его вызвать? как отложить вызов селектора? Что делать если селектор имеет много параметров? `(NSInvocation)`
- Что такое `быстрое перечисление (fast enumeration)`? 
- Что такое `делегат (delegate)`? Как его создать и использовать? 
- Что такое `notifications (уведомления)`? как мы должны их использовать?
- Какая разница между использованием `делегатов (delegation)` и `нотификейшенов (notification)`?
- Какая разница между использованием селекторов, делегатов и блоков?
- Что такое `KVO`? Когда его нужно использовать? Методы для обозревания объектов? Работает ли `KVO с instance переменными (полями)` объекта?
- Что такое `KVC`? Когда его нужно использовать?
- Какие существуют `root классы` в iOS? Для чего нужны `root классы`? 
- Как работает `proxy`?
- Что такое `тип id`. Что случится во время компиляции если мы посылаем сообщение объекту `типа id`? Что случится во время выполнения если этот метод существует?
- Цепочка ответсвенности, что происходит с методом после того как он не нашелся в объекте класса, которому его вызвали (в сторону forwardInvocation:)?
- Что такое `указатель isa`? Для чего он нужен?
- В чем разница между `NSArray и NSMutableArray`? непотоко-безопасный NSMutableArray?
- Чем отличается `NSSet от NSArray`? Какие `операции` происходят быстро в `NSSet` и какие в `NSArray`?
- Как удалить объект в ходе итерации по циклу?
- Как лучше всего загрузить `UIImage c диска(с кеша)`?
- Какой контент лучше хранить в `Documents`, а какой в `Cache`?
- `NSCoding, archiving`?
- Протокол `NSCopying`, почему мы не можем просто использовать любой собственный объект в качестве ключа в словарях (NSDictionary) , что нужно сделать чтобы решить эту проблему? (разница между глубоким и поверхностным копированием)?
- Суть `рантайма (Runtime), отправление сообщения`? Как работает Runtime?
- Как добавить свойство в существующий объект с закрытой реализацией? Можно ли это сделать через runtime?

Memory Management:
------------------
- Как происходит `ручное управление памятью - MRC` в iOS?
- `autorelease vs release`?
- Что означает `ARC`?
- Что делать, если проект написан с использованием ARC, а нужно использовать классы сторонней библиотеки написанной без ARC?
- `Weak vs assign`, `strong vs copy`?
- `Atomic vs nonatomic`. Чем отличаются? Как вручную переопределить atomic/nonatomic сеттер в не ARC коде?
- Зачем все свойства ссылающиеся на делегаты `strong/retain`. :))) 
- Что такое `autorelease pool`?
- Что такое `runLoop` `(NSAutoreleasePool)`, кодга он используется? `(timers, nsurlconnection ...)`?
- Как связаны `NSRunLoop и NSAutoreleasePool` на пальцах?
- Как можно заимплементировать `autorelease pool на с++`?
- Если я вызову `performSelector:withObject:afterDelay:` - объекту пошлется сообщение retain?
- Как происходит обработка `memory warning`(предупреждение о малом  количестве памяти)? Зависит ли обработка от версии iOS, как мы должны их обрабатывать?
- Напишите простую реализацию `NSAutoreleasePoll` на Objective-C?
- Когда нужно использовать метод `retainCount` (никогда, почему?) Объясните что такое `подсчет ссылок (retain count)`?
- Темы управления памятью, такие как владение `retain/release/autorelease`?
- Что случится если вы добавите только что созданный объект в `Mutable Array`, и пошлете ему сообщение `release`? Что случится если послать сообщение `release` массиву? Что случится если вы удалите объект из массива и попытаетесь его использовать?
- С подвохом: как работает `сборщик мусора` в iOS? :)))
- Нужно ли `ретейнить` (посылать сообщение retain) `делегаты`?
- Для чего используется класс `NSCoder`?
- Опишите правильный способ управления памятью выделяемой под `Outlet'ы`?
- Реализуйте следующие методы: `retain, release, autorelease`?

Networking:
----------
- Преимущества и недостатки `синхронного и асинхронного` соединения?
- Что означает `http, tcp`?
- Какие различия между `HEAD, GET, POST, PUT`? 
- Как загрузить что-то из интернета? В чем разница между `синхронными и асинхронными запросами`? Небольшое задание. Опишите как загрузить изображение из интернета и отобразить его в ImageView — все это должно происходить после нажатия кнопки.
- Что такое REST (Restful)?

Multithreading:
---------------
- С подвохом: вопрос о несуществующем параметре `atomic`, что он означает? Приведите пример кейса с использованием `atomic`?
- Как многопоточность работает с `UIKit`?
- Как запустить селектор в `(фоновом) потоке`?
- Как запустить `поток (thread)`? Что первым нужно сделать при запуске `потока`?
- Что такое `GCD`? Как `GCD` связан с многопоточностью? Типы queue и queue == thread?
- `NSOperation` vs `GCD`?
- Что такое `deadlock`?
- Что такое `livelock`?
- Что такое `семафор (semafor)`?
- Что такое `мьютекс (mutex)`?
- `Асинхронность` vs `многопоточность`. Чем отличаются?
- Какие технологии в iOS возможно использовать для работы с потоками. Преимущества и недостатки.
- Как запустить поток? Что первым нужно сделать при запуске потока? (NSAutoreleasePool - пул автоосвобождения) Что такое runLoop, кодга он используется? (timers, nsurlconnection …)
- Чем отличается `dispatch_async от dispatch_sync`?
- Для чего при разработке под iOS использовать `POSIX-потоки`? `pthread_create(&thread, NULL, startTimer, (void *)t);`
- А чем реально `POSIX-потоки` лучше чем `GCD или NSOperationQueue вместе с NSOperation`? Приходилось ри реально использовать POSIX и как в этом были прюсы? Реально, просто интересно…
 `Use POSIX calls if cross-platform portability is required. If you are writing networking code that runs exclusively in OS X and iOS, you should generally avoid POSIX networking calls, because they are harder to work with than higher-level APIs. However, if you are writing networking code that must be shared with other platforms, you can use the POSIX networking APIs so that you can use the same code everywhere. `

UIKit:
------
- Разница между свойствами `bounds и frame` объекта UIView? Понимание системы координат?
- Цикл жизни `UIViewController`?
- Что такое `View` (представление) и что такое `window` и цикл жизни `UIView`?
- Что такое `responder chain` (цепочка обязанностей, `паттерн chain of responsibility`, на примере UI компонентов iOS ), `becomeFirstResponder`.
- Что означают `IBOutlet` и `IBAction`, для чего они нужны, и что значат для препроцессора?
- Как работает `UITableView`? Жизненный цикл UITableView?
- Что можно сделать если клавиатура при появлении скрывает важную часть интерфейса?
- Почему мы должны `релизить IBOutlet'ты` во viewDidUnload?
- Что такое `awakeFromNib`, в чем разница между `xib и nib` файлами?
- Иерархия наследования UIButton.

Базы данных, CoreData:
----------------------
- Зачем нужно делать `двустороннии связи` в таблицах?
- Что такое `Core Data`?
- В каких случаях лучше использовать `SQLite`, а в каких `Core Data`?
- Что такое `контекст (Managed object context)`? Как происходят `изменения в NSManagedObjectContext`?
- Что такое `Persistent store coordinator`? Зачем нужен `NSPersistentStoreCoordinator`?
- Какие есть нюансы при использовании `Core Data в разных потоках`? Как `синхронизировать данные между потоками`(Как синхронизировать контекст)? Синхронизация разных типов NSManagedObjectContext (получение и изменение данных в child контекстах)? 
- Использовали ли `NSFetchedResultsController`? Почему? 
- Что такое `Fault` и зачем он нужен?
- Что таке `Fetched Property` и особенности работы с ним по сравнению с обычной связью?
- Как использовать `СoreData` совместно с `многопоточностью`?
- Что такое `NSManagedObjectId`? Можем ли мы сохранить его на потом если приложение закроется?
- Какие `типы хранилищ` поддерживает CoreData?
- Что такое `ленивая загрузка (lazy loading)`? Что ее связывает с CoreData? Опишите ситуация когда она может быть полезной?
- Что такое `нормализация` данных?
- Составить SQL запрос на выборку всех проектов  на которых сидит девелопер с id ==3. (Developers:id,name; Projects:id,name; Developers&Projects:project_id,developer_id)?

CoreAnimation, CoreGraphics:
----------------------------
- Что такое `CALayer`? 
- Чем отличается `UIView от CALayer`?
- Какие типы `CALayer` есть?
- Чем отличается `UIView based Animation от Core Animation`?
- Можно ли `отследить изменение alpha`, через KVO в CALayer?
- Тайминги в `CoreAnimation`?
- Что такое `backing store`?
- Чем отличаются `аффинные преобразования от трехмерных`?
- Нужно ли `ретейнить (посылать сообщение retain)` делегат для `CAAnimation`?

iOS Platform:
------------
- Какие бывают `состояния` у приложения?
- Жизненный цикл приложения? Что представляет из себя `Application Delegate`?
- Какого разрешение экранов iphon'ов, и в чем разница между `points (точками)` и `пикселями (pixels)`?
- Что такое `responder chain`?
- Как работают `push нотификации`?

Architecture
------------
- SOLID?
- Алгоритмическая сложность (big-o notation)?
- Что такое `VIPER`?
- Что такое `TDD` vs.`BDD`?
- Что такое `DDD`?
- Расскажите о `паттерне MVC`. Чем отличается `пассивная` модель от `активной`?
- Паттерн `MVC vs MVP vs MVVM`? https://habrahabr.ru/post/215605/
- Принципы `DRY`?
- Принципы `KISS`? 
- Что такое `IoC`? 
- Что такое Dependency Injection?
- Clean Architecture?

Паттерны:
--------
- Что такое `Фабрика (Factory)` и зачем она нужна?
- Реализация `синглтона (Singleton)` в `ARC` и в `non-ARC`?
- Назовите основные отличия `синглтона` от `статического класса`, и когда следует использовать один, а когда другой? 
- Как пересоздать синглтон? Можно ли `обнулить объект синглтона`?

Структуры данных:
----------------

С:
---
- Как представлены `Си-структуры` (CGRect, CGSize, CGPoint) в Objective-C?

Algorithms:
----------
- Напишите код, который `разворачивает строку на С++`. (переставить символы в строке в обратном порядке)?
- Поменять местами a и b не используя промежуточную переменную?
- Написать функцию вычисления n-го числа последовательности фебоначи. (если решить через рекурсию, спросят чем опасно такое решение)?
- Решить задачку о массиве: дан массив из 1001 элемента в котором присутсвуют все числа от 1 до 1000 и одно повторяется дважды, узнать какое, если к каждому элементу можно обратиться только 1 раз?
- Как из строки вытащить подстроку?
- В массиве 1001 число в диапазоне от 1 до 1000 включительно. Лишь одно число в массиве повторяется дважды. Надо за линейное время (и обратившись к каждому числу максимум один раз) найти продублированное число.

Logical:
--------
- Есть 4 человека, каждый проходит мост за 1, 2, 5, и 10 минут соответственно. Через мост они могут переходить только парами, держась за руку и только с фонариком. Притом один должен вернуться обратно и передать фонарик. Необходимо переправить всех за 17 мин на другую сторону. Задача решаема.

Code Puzzels:
-------------

- Что произойдет здесь (компиляция  + время выполнения): 

```objc
NSString *s = [NSNumber numberWithInt:3]; 
int i = [s intValue];
```

- Что не так с этим кодом? Зачем нужны `инициализаторы`?

```objc
[[[SomeClass alloc] init] init];
```

- Сработает ли `таймер`? Почему? 

```objc
void startTimer(void *threadId) 
{
   [NSTimer  scheduleTimerWithTimeInterval:10.0f 
      target:aTarget 
          selector:@selector(tick: ) 
          userInfo:nil
           repeats:NO];
}

pthread_create(&thread, NULL, startTimer, (void *)t);
```

- Какой метод вызовется: класса A или класса B? Как надо изменить код, чтобы вызвался метод класса A?

```objc
@interface A : NSObject
- (void)someMethod;
@end

@implementation A
- (void)someMethod
{
    NSLog(@"This is class A");
}
@end

@interface B : A
@end

@implementation B
- (void)someMethod 
{
    NSLog(@"This is class B");
}
@end

@interface C : NSObject
@end

@implementation C
- (void)method 
{
    A *a = [B new];
    [a someMethod];
}
```

- В каких случаях лучше использовать `strong`, а в каких `copy` для NSString? Почему?

```objc
@property (nonatomic, strong) NSString *someString;
@property (nonatomic, copy) NSString *anotherString;
```

- Что выведется в консоль? Почему?

```objc
- (BOOL)objectsCount
{
    NSMutableArray *array = [NSMutableArray new];
    for (NSInteger i = 0; i < 1024; i++) 
    {
        [array addObject:[NSNumber numberWithInt:i]];
    }
    return array.count;
}

- (void)someMethod 
{
    if ([self objectsCount]) 
    {
        NSLog(@"has objects");
    }
    else
    {
        NSLog(@"no objects");
    }
}
```

- Выведется ли в дебагер «Hello world»? Почему?

```objc
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
    dispatch_sync(dispatch_get_main_queue(), ^{
        NSLog(@"Hello world");
    });

   /* Another implementation */
   return YES;
}
```

- Что выведется в консоль?

```objc
 dispatch_async(dispatch_get_main_queue(), ^
    {
        NSLog(@"A %d", [object retainCount]);
        dispatch_async(dispatch_get_main_queue(), ^
        {
            NSLog(@"B %d", [object retainCount]);
        });
        NSLog(@"C %d", [object retainCount]);
    });
    NSLog(@"D %d", [object retainCount]);
```

- Что произойдет при исполнении следующего кода? 

```objc
Ball *ball = [[[[Ball alloc] init] autorelease] autorelease];
```
Additional:
-----------------------------
- Анкета в которой просят оценить свои знания по технологиям по 10 бальной шкале.

Programming:
--------
- Что такое `куча (heap)` и `стэк (stack)`? В какой памяти создаются объекты, примитивные типы и блоки?
- Что такое `полиморфизм`?
- Что такое `инкапсуляция`? Что такое `нарушение инкапсуляции`?
- Чем `абстрактный класс` отличается от `интерфейса`?
- Что такое сериализация объекта?
- Игра в `разбитые окна`?
- Что такое `регулярные выражения` (регулярки)?
- Что такое `перегрузка операторов`?
- Что такое `указатель`?

General:
- Ваше любимое видео с WWDC?
- Какое ваше любимое приложение и почему?
- Что нового появилось в iOS 10/iOS 9?
- Что такое парное программирование?


Swift
----------
- `Фундаментальные` типы и `коллекции`? 
- Aттрибут `@UIApplicationMain` ?
- Что такое `Bridge Header`? Как использовать Objective-C код в Swift проекте?
- Оператор `guard`?
- `Интерполяция` vs `конкатенация` строк?
- `let` vs `var`?
- `typealias`? Создание своего собственного типа?
- nil в Swift vs nil в Objective-C? Различия?
- Оператор `??`?

### Что такое свойство

`Свойства` - механизм автоматического создания `методов доступа` (getter/setter) для `внутренней переменной` класса (ivar), который появился в Objective-C 2.0

Свойства объявляются посредством `директивы @property` - компилятор автоматически создает методы доступа (сеттер/геттер), и необязательной `директивы @synthesize` - которая устанавливает `(@synthesize object = _object)` правила доступа к внутренней переменной.

