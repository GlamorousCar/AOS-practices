### Работа в командой строке ОС AstraLinux
---

Откроем терминал и посмотрим какой терминал сейчас соответствует активному виртуальному терминалу. 

Так как я пользуюсь виртуальной машиной в гипервизоре, и подключение осуществляется через VNC у меня 
не работет прокидывание некоторых сочетаний клавиш, поэтому переключение клавиш получилось только 
через команду chvt

![Снимок экрана 2023-10-26 151806](https://github.com/GlamorousCar/AOS-practices/assets/48102376/087b45da-700c-4a87-844e-9fab947f85a3)

Удалось сочетанием клавиш Ctrl-t открыть новый терминал

![Снимок экрана 2023-10-26 151922](https://github.com/GlamorousCar/AOS-practices/assets/48102376/cf3ed76d-a023-401d-878d-ff4266709898)

С помощью команды ``` fly-term & tty ``` определим в каком терминале происходит работа


![Снимок экрана 2023-10-26 152028](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5b4cda23-670a-486c-92f1-590c34b8b96d)
![Снимок экрана 2023-10-26 152032](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e7293645-82fa-4ffb-8478-cfac46d5f9b4)

Используя команду ```pwd``` получим вывод на экран пути к текущей рабочей директории.
![Снимок экрана 2023-10-26 152041](https://github.com/GlamorousCar/AOS-practices/assets/48102376/55695b43-0690-44a3-8d6d-07d6c3d421e5)

С помощью команды ```ls``` можно узнать содержимое директории
![Снимок экрана 2023-10-26 152123](https://github.com/GlamorousCar/AOS-practices/assets/48102376/d8f3ab35-6201-455a-bfc3-5bfddcf17c43)

Используя флаг ```-a``` на экран выведутся еще и скрытые файлы
![Снимок экрана 2023-10-26 152129](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a17e65f2-93ba-4db1-ac1f-c8497c846276)

```ls -h``` добавляет информацию к выводу о размере файлов в килобайтах 
![Снимок экрана 2023-10-26 152443](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9e1dcb04-668a-45b1-8060-01964c64cf38)

```ls -d``` выводит информацию не о файлах, а о директории
![Снимок экрана 2023-10-26 152742](https://github.com/GlamorousCar/AOS-practices/assets/48102376/43598dbe-b221-4a80-99ba-fb9895b70337)

Определим имя компьютера и имя пользователя

![Снимок экрана 2023-10-26 152812](https://github.com/GlamorousCar/AOS-practices/assets/48102376/3f524fb6-08a6-4f97-b2f6-6229b0bbdc12)

Получить список переменных окружения можно командой printenv и дополнительно воспользоваться командой grep.
```ptintenv | grep USER```

![Снимок экрана 2023-10-26 152853](https://github.com/GlamorousCar/AOS-practices/assets/48102376/4ab9ab47-dac9-48eb-91f9-64128efcdbef)
![Снимок экрана 2023-10-26 152911](https://github.com/GlamorousCar/AOS-practices/assets/48102376/651b0910-9167-482e-ada3-4dacb4d1d8e1)

Перейдем в каталог /etc

![Снимок экрана 2023-10-26 154718](https://github.com/GlamorousCar/AOS-practices/assets/48102376/391756ca-3cf3-4bf7-bc69-12c913671141)

Отобразим сожержимое файла passwd 

![Снимок экрана 2023-10-26 154855](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9d2a7f43-9854-410b-b7b9-08e3adbe3c19)

Отображается ли в этом файле пароли пользователей? Нет конечно не отображается

Просмотрим метаданные файла passwd. Команда ```stat имя_файла``` выводит содержимое inode
![Снимок экрана 2023-10-26 155536](https://github.com/GlamorousCar/AOS-practices/assets/48102376/35bf411c-d370-4057-8eb8-70c35cf463a8)

Команда ```ls -i имя_файла``` показывает номер индексного дескриптора и имя файла.

![Снимок экрана 2023-10-26 155557](https://github.com/GlamorousCar/AOS-practices/assets/48102376/82e5b4fb-e00a-4ee1-b5e8-281474e3e33c)

Команда ```df -i``` показывает количество занятых и свободных индексных дескрипторов в файловой системе.
![Снимок экрана 2023-10-26 155645](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ebf2ee96-5a2d-4af8-ab03-d72cc8c03ba0)

Вернемся в домашнюю категорию и Посмотрим название и версию дистрибутива, версию ядра, аппаратную архитектуру и версию основной системной библиотеки.

![Снимок экрана 2023-10-26 160454](https://github.com/GlamorousCar/AOS-practices/assets/48102376/36cc25eb-3d31-40f1-88a2-21bda4be285e)

![Снимок экрана 2023-10-26 160514](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e0022bed-305d-425e-90da-7068f2184341)

![Снимок экрана 2023-10-26 160540](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7b461061-5277-48f4-8149-077f9db3754b)

![Снимок экрана 2023-10-26 160551](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e0d2b5fc-60af-4910-8a61-dbe92864861e)

![Снимок экрана 2023-10-26 160609](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2687a956-11f7-4e2d-8e3a-f7a752ff2dd1)

![Снимок экрана 2023-10-26 160627](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9b1512ca-291a-49f7-8442-fa4d08c7f207)

Посмотрим список псевдонимов в системе, а также создадим свой псевдоним, который будет при удалении файлов или директорий ожидать подтверждения пользователя

![Снимок экрана 2023-10-26 161230](https://github.com/GlamorousCar/AOS-practices/assets/48102376/3b5a94ba-6d98-4766-80b9-a90cafad906f)

Используя команду ```sudo fly-fm``` откроем графический менеджер файлов

![Снимок экрана 2023-10-26 161309](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a8b20cef-c8f5-4558-a2dc-c08aa127b346)

Создадим два текстовых файла

![Снимок экрана 2023-10-26 165953](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6d406d47-2065-4873-a9eb-ab71f2a5a290)

Выведим информацию о характере содержимого файла с помощью команды ```file``` 
![Снимок экрана 2023-10-26 170030](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a24c9d2a-1495-4383-9494-9bf3ae42ff09)

Проанализируем две следующие команды:
```cd D1 || mkdir D1```
```mkdir D2 && cd D2```

В чем между ними разница?
1) Использование логического ИЛИ между командами означает, что:
- если первая команда была выполнена успешно, то вторая команда не выполняется;
- если первая команда завершилась неудачей, то выполняется вторая команда.
- 
Это мы и видим по выводу консоли
![Снимок экрана 2023-10-26 170149](https://github.com/GlamorousCar/AOS-practices/assets/48102376/d503e996-b7b2-4302-a9d0-c93bb7b02b90)
![Снимок экрана 2023-10-26 170153](https://github.com/GlamorousCar/AOS-practices/assets/48102376/fe0ea67b-5aff-463b-95f2-19a3f23bc7a1)

Посмотрим наличие свободного места в системе с помощью ```df –h```

![Снимок экрана 2023-10-26 170400](https://github.com/GlamorousCar/AOS-practices/assets/48102376/10d92fa2-287f-4e74-8900-f6d20442c604)

Создадим переменную user1 и присвойте ей значение 1. 
Далее получим значение этой переменной и создай новую переменную user2 со значением 2. 
Получим оба значения этих переменных. После чего удалим переменную user1.

![Снимок экрана 2023-10-26 171032](https://github.com/GlamorousCar/AOS-practices/assets/48102376/8c44481c-d552-4a26-8a6d-190e41b05899)

![Снимок экрана 2023-10-26 171102](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1b1d0505-0b52-4eb6-8c0a-843af1abc97b)

![Снимок экрана 2023-10-26 171129](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7510585e-f742-47e3-ae82-5284ecdfaf32)

Использую команду ```echo```. Посмотрим список файлов и каталогов в текущем каталоге, начинающихся с прописной буквы

![Снимок экрана 2023-10-26 172209](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ab99304b-52a8-4f81-b027-2aca1d64689c)

#### Использование справочных ресурсов

Откроем справку в графической среде

![Снимок экрана 2023-10-26 172255](https://github.com/GlamorousCar/AOS-practices/assets/48102376/29254a58-b2dc-4dfa-a52b-65c38e2b4fda)

Ознакомимся со справкой по fly-su
![Снимок экрана 2023-10-26 172415](https://github.com/GlamorousCar/AOS-practices/assets/48102376/4a8f77e3-e880-4178-9d79-7b54a1c5151e)

Воспользуемся поиском в справке

![Снимок экрана 2023-10-26 172433](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b497e39d-8f1d-4c37-93c4-b5ce4f870f0a)

Воспользуемся командой ```help``` чтобы вывесит справку по команде pwd

![Снимок экрана 2023-10-26 172641](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5d844acb-520b-4b0a-8357-650349e3e092)

Для просмотра и изменения атрибутов дисциплины линии воспользуемся командой stty
![Снимок экрана 2023-10-26 173248](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ba2b11ca-5cb9-49e4-99e4-fb48c47cde28)

Команда infocmp предназначена для вывода поддерживаемых указанным терминалом управляющих последовательностей. 

![Снимок экрана 2023-10-26 173358](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6df37795-a539-40e7-a2f7-00ceb1262ba4)

Утилита screen не установлена в системе.  И при попытки установить появляется ошибка 
![Снимок экрана 2023-10-26 173618](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ce8ac13a-295e-4cff-a760-deab04e2d294)

Поэтому я немного изменил файлы sourcelist. После этого установка пошла
![Снимок экрана 2023-10-26 174330](https://github.com/GlamorousCar/AOS-practices/assets/48102376/32e0b799-5cbc-4eb7-b6e6-3e8988168cce)

Установка завершена и программа работает
![Снимок экрана 2023-10-26 180343](https://github.com/GlamorousCar/AOS-practices/assets/48102376/eb86fbad-299c-4e1c-ad1e-807ce76ea5ce)
