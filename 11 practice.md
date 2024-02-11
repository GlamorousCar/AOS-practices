###  Запуск заданий по расписанию. Поиск и устранение неисправностей


Служба cron

Отобразим файл /etc/crontab и проанализируйте содержимое

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f6d36b57-3c1f-4e3d-8a37-5ba85b5f8d89)

Разрешим нашему пользователю работать со службой cron

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/bd6a2f8c-db9d-4b49-a42f-c55924d740f2)

Добавим задание через crontab -e, с помощью которого во втором открытом терминале будет выводиться сообщение «Hello cron» через 2-3 минуты после текущего времени

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/88ca4678-406e-40af-ab2f-ec51043eecc7)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/438b05d1-9385-4c8e-a814-89f582e8d36b)


Отобразим все задания, которые установлены в системе.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ee6759c3-428a-43ca-9358-69fe03a0c3eb)

Служба anacron

Отобразим и изучим содержимое файла /etc/anacrontab.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1d5a17e9-d9f8-409a-99ad-f50c3d9607d8)

Посмотрим, когда в последний раз был отработан скрипт cron.daily при использовании anacron.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/363d4c8b-a62c-449c-939d-f117b80323f1)

Запуск заданий по расписанию с помощью systemd

Отобразим содержимое юнита anacron типа service и timer через systemd.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a1066043-a61b-4486-ac43-a1d4ba9c490b)

Установим утилиту at для запуска отложенных заданий, которые будут выполняться в системе всего один раз.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/52d0c38c-7ca0-485b-89eb-f69b8e739161)

Создадим задание, которое выведет во второй терминал сообщение «Hello at» через 4-5 минут.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5974d18d-4219-4cae-997f-eb8973e734d7)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f8c96014-1487-491d-ba0a-b3ab5683c7d3)

Поиск и устранение неисправностей

Проанализируем, когда в последний раз произошла перезагрузка системы. 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ea5fcce5-9dc3-4a80-8d78-1692ff7acdd3)

Отобразим сообщения, которые выводились в момент предыдущей загрузки системы.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f5f74282-1f6e-40fe-800c-008301173221)

Включим возможность снимать дампы памяти в файле /etc/security/limits.conf.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7a1901e6-1ded-42be-90a7-6917b930499e)

Создадим отдельный каталог для дампов

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a7344ed8-a184-4cf0-aaf9-bcacaa5f113d)

Укажем формат и место сохранения дампов в /etc/sysctl.conf.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/03320bf3-1ba2-406c-aad4-6711f3684a5a)

Загрузимся в режиме восстановления системы. Посмотрим, в каком режиме смонтирован корень

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/68d9e49f-e2bb-41db-86a9-d772a60f3c26)

Установим обязательную проверку системы на ошибки. Измените параметр Check interval на 1 месяц.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ae9c8b90-6b0d-4897-8a2e-5f91c3114164)

Дополнительно

Запуск отложенных заданий с помощью systemd-run.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e89bcb04-ebce-42e9-9063-a3d3f8ea26b2)
























