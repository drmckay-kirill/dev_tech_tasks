# 2022 - 2023
# II семестр

## Мегалаба: свой проект (5 человек, от 20 до 40 баллов - зависит сложности)

Придумать идею своего проекта.
Надо, чтобы люди были разбиты по специализациям, каждая роль будет защищать/объяснять свою область.


frontend - пользовательский интерфейс (веб или десктоп)

backend - серверная логика


QA - написать автоматизирированные тесты для вашего приложения, автоматически приложение запускается и проходят сценарии (selenuim etc)


devops - сделать развёртывание/деплой вашего приложения, чтобы не запускать из VisualStudio проекты.

Собраться группой, выбрать тему, попробовать выбрать технологии - прийти к преподавателю, определимся с реализацией.

## Мегалаба: Теплица (40 баллов, 5 человек)

Разработать веб-приложение сбора и визуализации температурных данных и управления теплицей.

Веб приложение должно иметь возможность регистрации пользователей. Пользователь может приобретать контроллеры температуры, освещенности и влажности почвы. Каждый контроллер имеет  128 битный идентификатор. Пользователь может добавлять контроллеры в рабочем кабинете, присваивать им имена, группировать их (теплица 1, теплица 2 и тд). Контроллер температуры имеет следующие настройки: температура начала/окончания проветривания, температура начала/окончания подогрева, верхняя и нижняя предельная граница температур для отправки экстренных сообщений (почта, или смс, или телеграмм, etc). 

Контроллер освещенности имеет следующие настройки: требуемая длительность светового дня

Контроллер влажности почвы имеет следующие настройки: влажность включения и отключения полива.

У каждого контроллера можно задать интервал обновления. По умолчанию интервал равен 5 минут.

Контроллер температуры при включении передает веб серверу свой 128 битный идентификатор и показания температурного датчика. Сервер регистрирует показания и в ответ присылает текущие настройки для контроллера: интервал времени для отправки температурных данных, температура включения/отключения подогрева, температура открытия/закрытия форточек для проветривания. При достижении критических температур производится отправка уведомлений.

Контроллер освещенности передает веб серверу свой 128 битный идентификатор и показания датчика освещенности. Сервер в ответ сообщает контроллеру время до отключения подсветки или 0 если подсветка не требуется. Сервер регистрирует текущую освещенность и основываясь на настройках принимает решение о подсветке на требуемое время после падения освещенности.

Контроллер влажности передает веб серверу свой 128 битный идентификатор и показания датчика влажности. Сервер регистрирует текущую влажность и отправляет контроллеру текущие настройки влажности для включения и отключения полива.

Рабочий кабинет также имеет возможность мониторинга текущих показаний данных датчиков и отображения их во времени (графики) за указанный период (несколько часов, дней, месяцев). А тахже хранение истории отправленных уведомлений/команд.

Контроллеры эмулируются отдельными приложениями/сервисами. По приложению для контроллеров влажности, освещенности, температуры, etc. При запуске каждого экземпляра контроллера необходимо конфигурировать идентификатор: вводить вручную, через файлы, переменные окружения, и т.п.

## Клиент-серверная игра (1 человек)

Реализуем клиент-серверную игру разными способами. Реализовали одним способом - сдали - делаем следующий.
Игра должна быть для двух игроков, игроки подключаются к серверу, сервер находит им соперника, сервер передаёт данные между игроками. Например: морской бой, крестики-нолики, камень-ножницы-бумага и т.п.

| Клиент              | Сервер          | Протокол          | Баллы             |
| -----------         | -----------     | -----------       | -----------       |
| Консоль             | Консоль         | TCP               | 6                 |
| Консоль             | Консоль         | HTTP              | 6                 |
| Консоль             | Веб фреймворк   | HTTP              | 6                 |
| Браузер HTML/js     | Веб фреймворк   | HTTP              | 6                 |
| Браузер             | Веб фреймворк   | WebSocket/SignalR | 6                 |

Во 2 строке имеется чисто взаимодействие по HTTP протоколу без всяких фреймворков, например, со стороны сервера на C# поднять простой HttpListener.

## Обычные лабораторные (1 человек)

## Файлы по UDP (3 балла)

Разработайте клиентское и серверные приложения, позволяющие принимать и передавать файлы **любого размера** по UDP.

## Нагрузочное тестирование (5 баллов)

С помощью вашего языка и его библиотек сделайте нагрузочное тестирование сервера из предыдущей лабораторной. Сколько подключений он может выдержать, как зависит RPS от размера файлов?

Для C# можно использовать https://nbomber.com/.

## Именованные каналы (3 балла)

Разработайте клиентское и серверные приложения, позволяющие принимать и передавать файлы, используя именованные каналы.

## ООП и Excel/Word (8 баллов)

Подготовьте рабочую книгу Excel с записями когда, какому студенту, из какой группы, по какому предмету и какой балл был выставлен. 
Разработайте классы и интерфейсы в вашем приложении: оценка, студент, группа и группы. 
Класс группы должен содержать метод загрузки данных из файла Excel, свойства количество групп и сами группы. 
Группа должна иметь свойства количество студентов и самих студентов. 
А студент должен иметь свойство количество оценок и сами оценки. 
Кроме того классы должны иметь вычислимые свойства: для класса студент должно быть свойство баллы означающее общее количество заработанных им баллов, группа должна иметь свойство средний балл. 
Классы группы и группа должны иметь методы вывода себя в указанный шаблон ведомости файла Word.

в .NET для работы с Office смотрите в сторону https://learn.microsoft.com/ru-ru/dotnet/csharp/advanced-topics/interop/how-to-access-office-interop-objects или https://www.epplussoftware.com.

# I семестр

## 1 Бинарные деревья (4 б., + 1 б. за другой ЯП)
Генерировать 10^6 (10^3) случайных чисел в [- 10^7; 10^7] [- 10^4; 10^4]. Поочередно вставлять в бинарное дерево.
Генерировать новые 10^6 (10^3) случайных чисел в [- 10^7; 10^7] [- 10^4; 10^4]. Поочередно выполнять поиск в бинарном дереве.

## 2 Очередь с приоритетом (3 б., + 1 б. за другой ЯП)
Генерировать 10^6 (10^3) случайных чисел в [- 10^7; 10^7] [- 10^4; 10^4]. Поочередно вставлять в очередь. Черзе каждый 1000 элементов доставать 500.
https://acm.khpnets.info/wiki/Очередь_с_приоритетами

## 3 Работа с динамическими библиотеками (4 б.)
Разработайте приложение. В папке приложения находится папка PLUGINS с динамическими библиотеками, содержащими функции TheFunc(x: Double): Double (cdecl) и функцию FuncName: PAnsiChar (stdcall). Приложение загружает библиотеки, выводит имена функций и спрашивает пользователя какую функцию посчитать. После ответа, программа либо строит график на интервале от 0 до 10 и подписывает его названием функции. Если библиотеку загрузить не удалось или функции не найдены, то она пропускается. 
Файлы к лабораторной работе https://drive.google.com/file/d/1W2zIbjRYHnKRz50IXzOeE69B2itCmpds/view?usp=sharing, пароль - 123

## 4 Очередь с приоритетом в отдельной динамической библиотеке DLL (4 б., + 1 б. за другой ЯП)
https://hwmw.blogspot.com/p/windows-dll.html

## 5 Очередь с приоритетом в ActiveX/COM объекте (4 б., + 1 б. за другой ЯП)
https://github.com/drmckay-kirill/dev_tech_labs/tree/master/ActiveXDemoLib
https://github.com/drmckay-kirill/dev_tech_labs/tree/master/ComDemoLib/ComDemoLib

## 6 Очередь с приоритетом и синхронизацией доступа (мьютекс/семафор) (4 б.)
N потоко пишет в очередь. M потоко читает из очереди. Запустить параллельно.

## 7 Очередь с приоритетом и синхронизацией доступа через вызовы WinAPI (4 б.)
ресурс с инфой - pinvoke.net

## 8 Git: ветвления (2 б.)

## 9 Git: precommit (4 б.)
Надо написать githook, если точнее precommit. Который будет вносить изменения в ваш исходный код, например конкретнее:
- заменять все слова типа PASSWORD на случ символы.
- если в вашем коде будет фигурная скобка последним символом в строке то перенести её на другую строку (для python можно другой пример форматирования).
Ваш проект с гитхуком должен быть в репозитории на гитхабе:
- делаете новую ветку
- делаете в ней изменения, которые правятся вашим хуком
- коммит
- если надо комимит с изменениями от хука (как это решать?)
- пуш ветки
- делаете pull request и аппрувите его ваш репозиторий должен быть публичным, чтобы по истории комитов можно было увидеть все манипуляции. 
Это стандартный flow разработки, через feature-ветке и мёрдж-реквесты.


## 10 Гонки в консоли (5 б.)
Каждый участник гонки - отдельный поток, который свой уникальный символ в консоли в одной строке. Пишет через разные случайные промежутки времени. Запустить N потоко параллельно.
Консоль должна выглять во время работы программы примерно так:
#####

@@

!!!!!!

????????

$


...

для .NET доп. баллы: 
попробовать разные встроенные способы синхронизации - Mutex, Semaphore, SemaphoreSlim, Monitor, SpinLock. Объяснить разницу между ними (+ 7 б.). 
Попробовать замерить их скорость работы, кто будет быстрее, использовать StopWatch или посмотреть как мерять конкуретные операции в BenchmarkDotNet (+ 5 б.). 
Стартовать потоки одновременно по нажатию клавиши, смотреть в сторону ManualResetEvent (+ 4 б.).

## 11 Использовать разделяемую память для хранения полей гонки (5 б.). 
То есть каждый поток пишет не в консоль символ напрямую, а в участок разделяемой памяти. А уже основной поток выводит на консоль текущее положение в гонке.

## 12 Для .NET: LINQ и BenchmarkDotNet (8 б.)
Используя библиотеку бенчмарка, сделать замеры методов над коллекциями, объяснить почему некоторые из них быстрее, почему некоторые используют больше памяти.
Объяснить, что такое IEnumerable, LINQ.
Не забыть включить MemoryDiagnoser, в некоторых случаях также надо будет включить Locking Allocations (чтобы посмотреть сколько блокировок было использовано).

1) Переборы над массивом Array
- foreach
- обычный for
- while

2) взять первые три элемента из массива
- Take
- через итератор
- свой способ

3) взять последние три элемента из массива
- Last
- через итератор
- свой способ

4) Перебор списка List
- foreach
- обычный for
- while
- For из LINQ
- CollectionsMarshal.AsSpan

5) Перебор ReadOnlyList

6) Перебор ImmutableList

7) Сортировка списка List
- Sort
- OrderBy
- свой способ!

8) Вставка в
- обычный словарь Dictionary
- ConcurrentDictionary

9) Поиск в (использовать разные размеры - 3, 10, 100, 1000)
- List
- ImmutableList
- HashSet
- ImmutableHashSet

## 13 -

## 14 Мегалаба (25 б.)
Написать пошаговую игру для двух человек. Но так чтобы логика отображения была отделена от логики самой игры. А именно: у нас есть отдельный процесс/ActiveX(COM)-сервер, который обрабатывает данные от двух игровых приложений. Игровые приложения - это десктопное и консольное приложения. Они знают только как выводить игру на экран и ничего не знают про логику игры.
Взаимодействие проектировать самим.
Мегалаба можно делать в группе до 5 человек.
