### Создание сценариев bash

##### 1. Создание и запуск простых скриптов, использование конструкции if then

1.1. Создайте пустой файл с произвольным именем. В первой строке укажите, какая именно оболочка будет использована для обработки сценария.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/4ffeb2e0-a9ba-4b75-9b7f-ffc80c44dbbe)


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7e8a3715-bdba-4a1f-a09a-e8fb15eeda3d)

1.2. Добавьте в скрипт команды, которые будут выводить текущую директорию и пользователя.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/60cdc76e-bf2c-4203-ba4a-f2c91e71dd00)

1.3. Сделайте файл исполняемым и запустите сценарий.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b28adfd6-9eff-4c35-8b48-675f5f38cd81)

1.4. Сделайте так, чтобы текущая директория и пользователь выводились с помощью переменных окружения.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6bdc88ec-9312-4a64-8943-8e6a435e9319)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/8ab98572-1375-47cf-9069-943739d24949)

1.5. Добейтесь такого же результата с помощью объявления собственных переменных.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/506f63b7-2db0-4858-805f-2e474a63afee)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/66f07842-acea-4db9-9e8a-ae3f12b439ff)

1.6. Дополните сценарий: необходимо найти пользователя user1 в /etc/passwd. Если его удалось найти, то сообщить о том, что он существует. Если нет – вывести сообщение о том, что такого пользователя не существует.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7172e983-dd94-47ec-a7ac-066683524b73)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/8a956162-07b8-4ad6-9afa-0c5be9061395)

1.7. Проверьте существование директории AstraLinux, перейдите в нее и выведите ее содержимое на экран.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/dc191d6d-491d-4118-a5eb-e9ca9412eec6)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/704c0d51-0166-4e5f-944e-ea12a35eb4ce)

1.8. Усложните сценарий: проверьте существование директории DBMS и файла file1 в директории DBMS/MongoDB. Если они существуют, то вывести содержимое директории DBMS и файла file1. Если нет, вывести сообщение. 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ae32b2e3-e279-4e22-94cf-eb1325ad5ac9)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/431b4ca8-7d36-4d47-bc3b-357abeee15a0)

Файлов не существует, так работа с этой практики началась с новой ВМ , весь прошлый прогресс потерян

##### 2. Циклы for

2.1. Рассмотрите разницу между выводом файла /etc/passwd, где разделителем является знак перевода строки и знак двоеточие.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/fa474423-0147-4e06-90a0-47ded39ae050)

Результат работы

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e9eaceaf-152b-40be-b18b-d57bf4251a7a)

После смены разделителя

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b86c55b3-9670-436d-8186-b45d62582a69)

Результат

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2870f89a-71ef-4558-80a0-9b125b175330)

2.2. С помощью цикла создайте пользователей user4, user5 и user6. Отобразите в /etc/passwd только те строки, в которых есть слово user.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/cf240951-64ee-425d-a84a-67844850be6e)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/cdc931ee-ff4a-48cb-be9a-f70d01f08b34)

##### 3. Сценарий для crontab

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/bb295b0a-b219-4124-af6b-282b6619d347)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f5b422a7-0fa3-4e93-a2d7-b31301107fd1)


3.2. Создайте задание для crontab, которое будет выполнять сценарий mem_monitor и записывать результат в файл memory. Для более быстрой проверки результата сделайте так, чтобы сценарий отрабатывал каждую минуту.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0c44d764-9f58-4a2f-8e43-f879f9662c20)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/4c07ef36-84ad-4a7f-92ef-15808db9a765)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5956afca-dc03-439e-8298-e399914ec49d)

4. Сценарий для автоматической настройки сети через nmcli

4.1. Отобразите сетевые настройки интерфейса eth1. Используйте эти параметры для дальнейшей работы.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/16c21c6d-3f80-496e-b4db-8c61049e129f)

4.2. Напишите сценарий, который будет автоматически настраивать сетевые параметры для интерфейса eth1 с использованием статического адреса.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/67a491af-e6fb-4473-83c1-407b84f51996)

4.3. Для проверки отправьте эхо-запрос на адрес интерфейса eth1 и адрес шлюза.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/82ad490b-3683-4460-980b-2dc06155eee6)




