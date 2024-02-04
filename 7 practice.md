###  Управление процессами

Отобразим список процессов системы без и с использованием опций с помощью команды ps.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ef970fdb-1ae2-46da-99ef-c12aa408a059)

Получим выборочную информацию обо всех процессах в системе. Включим в формат: состояние, ID процесса, номер терминала и команду, которая запустила процесс.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6f92ada2-446a-4abb-bdd1-fe5f98075fda)

Отобразим состояния процессов в реальном времени.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/00da70ee-9bc4-4057-815a-f89d715c45c7)

Получим справочную информацию по утилите top, находясь в интерактивном режиме работы этой утилиты 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/276a4286-0cab-4f40-81c1-57e84ef7e717)

#### Управление процессами

Выведем список процессов пользователя root, используя команду ps

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/88684667-2b85-4690-a14e-ef4ef679eb7c)

Количество процессов

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/c9c033bb-3c98-4afb-8dfb-734604d64766)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ff01a7c2-642d-4ce0-94da-d302336f3c98)

Получим информацию о процессах пользователя, имеющих статус роботоспособный

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/219ed2f0-f67f-4be8-bccc-9444195593b8)

Добавим к файлу proc1 сведения о процессе в данный момент потребляющий большой процент ресурсов центрального процессора

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/efe9a937-6b79-4ec8-99c5-30d6dfd117c9)

Запустим браузер firefox в фоновом режиме в втором терминале

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/4b7ea01a-da73-4e57-96ac-18f6d819e593)

В первом терминале найдем первый запущенный процесс с помощью команды ps и перенаправим вывод этой команды на ввод команды grep. Определим ID процесса и номер терминала.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/dae7b050-3add-4675-b550-9a4201cb3305)

Вернемся в первый терминал и найдем поддерево для процесса firefox, изучим список составляющих его процессов
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f58f1d36-aabe-4b63-9a80-c1ec070527f3)


Изменим приоритет для процесса, порожденного программой firefox. Сделаем его равным 10. Подтвердим, что приоритет изменился

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9500245e-b5ca-4cb0-a53d-6994783cafc2)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/8433cf64-f429-4b64-8a9d-0cee6baedeba)

Воспользуемся командой sleep для ввода задержки на 200 секунд и получите список заданий текущей сессии терминала. Обратите внимание, что задание sleep завершится через 200 секунд.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2c8dc1b6-2efa-4cfd-9b19-f5732afcc481)

Получим список сигналов для команды kill. Завершим запущенный процесс firefox двумя способами: с помощью сигналов SIGKILL и SIGTERM

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/fb63cdf4-51ec-46d9-95f1-537fcd149343)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7012349b-2ffd-47c7-b37d-ffc22af49e47)

Отправим сигнал SIGKILL заданию sleep.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9a637dd3-3d2a-4ebe-a6d8-020d83776b95)

Завершим все процессы вашего пользователя с помощью команды killall.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ff7d3702-966b-4cb0-9ba2-0fbfdea106fe)

Изучим информацию о доступе к общим библиотекам и просмотрим конфигурационные файлы.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2429166a-2730-49de-b73d-a7a46f39fd19)

Именования общих библиотек: имя.so.версия или имя-версия.so.
Команда ldd имя_программа показывает, какие общие библиотеки требуются для запуска динамически скомпонованной программы.
Настройка местонахождения общих библиотек производится с помощью конфигурационного файла /etc/ld.so.conf или conf файлов в /etc/ld.so.conf.d.
В конфигурационные файлы помещаются имена каталогов, содержащих общие библиотеки.
Команда ldconfig создает кэш, в котором хранится информация о всех библиотеках (/etc/ld.so.cache).
Команда ldconfig -p выводит список библиотек, хранимый в кэше.



