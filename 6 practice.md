### Управление учетными записями пользователей и групп
Изучим содержимое файла /etc/passwd

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9e0948db-358b-4a0c-892c-d1cd91d78cb4)

Изучим содержимое файла /etc/shadow

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/d65a1619-1afe-45b5-aaf5-32b5273f1a47)

Изучим содержимое файла /etc/group

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/4657ebc2-5557-41e7-b0f9-c886b94f9f92)

Изучим содержимое файла /etc/gshadow.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/3d13f043-a15a-42cb-9d9d-896ee0c79833)

Изучим содержимое файла /etc/login.defs.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9a96da02-7b14-49fa-aa25-1cef0c4bcf9d)

Просмотрим информацию о существующих пользователях системы

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6720db4d-4179-41d9-a68f-ea67be30d0ba)

#### Создание и управление учетными записями пользователей

Утилиты для работы с учетными записями:
useradd – создание учетной записи пользователя;
usermod – изменение параметров учетной записи пользователя;
userdel – удаление учетной записи пользователя;
groupadd – создание учетной записи группы;
groupmod – изменение параметров учетной записи группы;
groupdel – удаление учетной записи группы.

С помощью команд useradd, groupadd, passwd создадим учетную запись user1 со следующими параметрами:
– UID – 1500;
– основная (первичная) группа user1 (GID 1500);
– дополнительная группа – video;
– домашний каталог должен быть создан;
– входной командный интерпретатор – /bin/bash;
– задать пароль по своему усмотрению;
– время действия пароля – 60 дней;
– пользователь должен сменить пароль при первом входе в систему.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9956c0de-fdbe-4c28-aa12-7d2d106ad5ff)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/32275c14-020c-4702-b1ed-e1b249d50ee3)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0d4f9c68-0425-4db8-be2a-c98741e66b75)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/127ec81f-a5e4-492b-ac2a-26f64e665f96)

Проверим, что атрибуты учетной записи и параметры пароля установлены верно

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1fcab4c3-b2f3-4683-9551-a84cfb86998d)

С помощью утилиты adduser создадим учетную запись user2 со следующими параметрами:
– UID – 2000;
– основная группа user2 (GID 2000);
– дополнительная группа users;
– GECOS: полное имя – Пользователь 2, номер комнаты – 111, рабочий телефон 111-111, остальные поля пустые;
– зададим пароль по своему усмотрению.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/efe4f802-eedc-4a91-b721-9adf915e4efd)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0f4aac23-8348-417a-9e35-afd81a5ce102)

Проверим, что учетная запись пользователя user2 создана согласно требованиям из предыдущего пункта 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b87b84d2-57f7-4f55-8670-cc975e9d3d36)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/415dec97-ca0a-4b4b-a379-e3fa06e98a3f)

С помощью графической утилиты создадим учетную запись user3 со следующими параметрами:
– UID – 2500;
– основная группа user3 (GID 2500);
– дополнительные группы: users, cdrom;
– задайте пароль по своему усмотрению;
– время действия пароля – 30 дней;
– минимальное время между сменой пароля – 14 дней;
– время неактивности пользователя после окончания действия пароля – 60 дней.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/d1885754-ed74-4ce9-a880-26b6ce20ca83)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/21182aa5-bbb2-484b-b20c-2c78494cafe8)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/8d5a6711-2f83-4e79-b1d4-9d4ff19fb934)

Сделаем пользователя user2 администратором

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/78bbc191-bc7f-4134-8a41-672d312655c3)

Заблокируем учетную запись user3

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/11b09081-5c4c-4984-a9ec-15cdf238fd00)


