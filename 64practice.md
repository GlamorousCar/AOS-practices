![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a27ad1a9-634b-40e8-97c4-49cc42131c89)![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/642de388-560c-4912-b5a2-4f0fe30f2a26)Практическая работа № 4. Управление конфигурациями хостов с помощью Ansible

1. Установка ansible, использование ansible в командной строке и создание файла инвентаризации
1.1. Установите ansible на ВМ client1.
   
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5dc54df5-986b-429d-9b8f-deb1f2e4e2bc)

1.2. Настройте на ВМ client1 SSH-аутентификацию по ключам с хостом server1.
Примечание: это должно было сделано ранее в работе №2 «Настройка удаленного доступа».
Дальнейшие действия осуществляются под учетной записью администратора системы.

1.3. С помощью команды ansible посмотрите время на ВМ server1.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0dbe8002-03cf-47fa-b538-c1b376a49c1e)


1.4. Создайте в домашнем каталоге подкаталог ansible и перейдите в него. Дальнейшие действия осуществляются в созданном каталоге.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/cbd65936-38b7-4b3d-94b1-c366c8b7a95c)

1.5. Создайте файл hosts, в который нужно добавить следующую конфигурацию:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/324a1fab-fb07-44dc-a560-8ce580c72fda)

1.7. Создайте плейбук apt_update.yml, который будет обновлять локальный кэш репозиториев. Используйте пробелы для отделения строк, табуляция запрещена. Секции hosts, become, apt, debug должны располагаться строго под секцией name.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/281f00ab-f703-4728-9c3a-2e184aa83675)

1.8. Запустите плейбук.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/88c754e1-c9b0-4678-9c2c-fee0b66baf0c)

2. Создание ролей в Ansible
Ансибл-роль – это концепция в Ansible, которая имеет дело с идеями, а не с событиями. По сути, роль – это уровень абстракции, используемый для упрощения написания файлов playbook. Роль обеспечивает основу для многократно используемых компонентов, таких как переменные, модули, задачи и факты, которые могут быть загружены в файл playbook.
Одним из основных преимуществ использования ролей является то, что каждая роль не зависит от другой. Выполнение одной роли не зависит от выполнения другой роли. Кроме того, роли можно изменять и повторно использовать, что устраняет необходимость переписывать пьесы (play) и задачи (task) в файле playbook.
Предположим, что мы хотим создать файл playbook для установки серверного ПО на сервере server1. Лучше всего начать с создания трех отдельных ролей, каждая из которых будет устанавливать Apache, PostgreSQL и git соответственно на удаленный хост. Затем напишем playbook и вызовем роли в файле playbook.

2.1. Создайте 3 роли: git, postgresql, apache. Посмотрите структуру каталогов ролей, выполнив команду tree.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/778d3f27-e222-4c49-a81d-5b4d46bd5976)

2.2. Отредактируйте файл main.yml для директории git.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/887c2272-1c12-4b92-9943-f6f7bc3c5608)

2.3. Отредактируйте файл main.yml для директории postgresql.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/4f356779-de71-4acd-af7b-96d8d8945a3d)

2.4. Отредактируйте файл main.yml для директории apache.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/603a438d-b1eb-407a-95be-4d5310357308)

2.5 Создайте файл плейбук в директории ansible с именем apt_install.yml и укажите созданные роли.


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/bbdf617c-e314-4c1b-8de7-ea01cf0230cb)


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/535933b1-5b2d-41e4-b46a-6b57a235c52c)
