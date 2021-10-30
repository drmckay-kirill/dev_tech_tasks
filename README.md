# Первое дополнительное задание
### Работа с бинарными деревьями (5 баллов)
### Цель: немного познакомиться с индексами, которые часто используюся в СУБД
1 - генерируем 1_000_000 случ строк одинакового размера (Guid.NewGuid например)
2 - каждой строке присваиваем некий случайный идентфикатор, например - хэш строки или случайное целочисленное значение
3 - каждую строку с идентификатором последовательно сохраняем в файле данных
4 - для каждой строки: идентификатор строки и её смещение в байтах в файле вставляем в бинарное дерево из первой лабы (ключ - идентификатор, значение в узлах - смещение). Это нужно чтобы в дальнейшем по ключу находить смещение строки в файле. Такая структура данных называется индексом, часто используется для поиска данных
5 - берём 1000 любых идентификаторов строк из ранее сгенерированных и смотрим что быстрее:
5.1 - последовательный поиск строки в файле?
5.2 - поиск смещения в индексе, затем чтение из файла по смещению?

# Второе дополнительное задание
### kernel32 (10 баллов)
### Цель: использовать системные вызовы, познакомиться с .NET изнутри, почувствовать себя разработчиком высокоуровневого языка
### предпочтительнее использовать C#, python и ОС Windows
1 - Написать статический класс со статическими методами (по типу File, Console, etc) - записи в файл, чтения из файла.
Для работы с файлами использовать напрямую системные вызовы (windows - kernel32.dll).
Разработчикам на C# - изучать механизм P/Invoke (https://professorweb.ru/my/csharp/optimization/level6/6_2.php, http://pinvoke.net/default.aspx/kernel32.ReadConsoleInput).
Разработчикам на Python - смотреть в сторону библиотеки ctypes.
Можно поизучать как устроен фреймворк .NET изнутри (https://github.com/dotnet/runtime/tree/main/src/libraries/Common/src/Interop/Windows/Kernel32), для работы с ОС используются те же самые вызовы.
2 - генерировать 1_000_000 случ строк любого размера. Записывать их файл двумя способами - с помощью своего кода, стандартными средствами языка. Что быстрее?
3 - читать сгенерированный файл двумя способами. Что быстрее?
4 - сделать методы для работы с консолью: вывод строки, вывод отдельных символов в позицию, покраска консоли. +5 баллов

# Третье дополнительное задание
### Git (5 баллов)
### Цель: научиться пользоваться одним из основных средств разработчика - системой контроля версий
1) надо написать githook, если точнее precommit. Который будет вносить изменения в ваш исходный код, конкретнее:
- заменять все слова типа PASSWORD на случ символы.
- если в вашем коде будет фигурная скобка последним символом в строке то перенести её на другую строку (для python можно другой пример форматирования).
Хуки часто применяются для форматирования кода, чтобы держать его в чистоте и аккуратности.
2) ваш проект с гитхуком должен быть в репозитории на гитхабе
- делаете новую ветку
- делаете в ней измеения, которые правятся вашим хуком
- коммит
- пуш ветки
- делаете pull request и аппрувите его
ваш репозиторий должен быть публичным, чтобы по истории комитов можно было увидеть все манипуляции
Это стандартный flow разработки, через feature-ветке и мёрдж-реквесты.

# Четвёртое дополнительное задание
### Docker (4 балла)
### Цель: докер де-фактор сейчас стандарт для упаковки приложений, с ним надо быть знакомым
Вообще докер необходим:
- для поднятия внешних зависимостей в локальном окружении (на компьютере разрабочтика), всяких СУБД, очередей и прочего. Чтобы не ставить на комп по 100500 приложенй
- для упаковки разработанных приложений в единый формат со всеми зависимостями, чтобы в рабочем окружении для пользователей поднять ту же версию, что проверил разработчик и тестировщики
В этом задании необходимо упаковать ваше приложение из 1 лабы про бинарные деревья в докер-образ и запустить на его основе контейнер:
1. Создать Dockerfile для вашего приложения
2. Запустить на основе докер файла контейнер (docker build, docker run)
3. Показать список, список контейнеров, логи контейнера - чтобы доказать что всё работает.
4. Подсоединить к контейнеру локальную папку хоста и записать итоговый файл из лабораторной в неё. + 2 балла

# Пятое дополнительное задание
### Конкурентность, многопоточность (4 балла)
- Сгенерировать одновременно N (N > 10) файлов с 100_000 строк следующего вида: `порядковый номер файла: M случайных букв латиницы (M одинаково для всех файлов)`. **Одновременно** - использовать потоки
- **Одновременно** читать эти файлы и записывать строки в один итоговый файл.
Сколько строк в итоговом файле?
