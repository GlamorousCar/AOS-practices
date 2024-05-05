### Мандатный контроль целостности в ОССН. Мандатное управление доступом в ОССН. Реализация мандатного управления доступом в файловой системе

##### 1. Локальные политики безопасности и работа с учетными записями пользователей и группами

1.1. Запустите графическую утилиту редактирования учётных записей пользователей «Политика безопасности» через меню «Панель управления» главного пользовательского меню. Модифицируйте параметры мандатного управления доступом:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/8270647c-3904-48a5-84d7-3bf50fdb08e9)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/91a1606a-8efc-4c17-946b-8fba2e0b32a7)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/34e8e0ac-3b95-44a8-bf7d-607323f10419)

1.2. Создайте учётную запись пользователя user1, установив максимальный уровень доступа: «Уровень_4».

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/bc486941-8021-4a43-9062-34d3865e9cbb)

1.3. Попробуйте удалить уровень доступа 4 из раздела «Уровни конфиденциальности» путём выбора в контекстном меню пункта «Удалить».

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b8f6547d-6aaf-45b7-815f-cb53993eb78c)

1.4. Выведите в терминал Fly параметры мандатного управления доступом для учётной записи пользователя user1. Для этого выполните следующие действия:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a7191db6-3017-4913-bf18-7c1f3d4e1290)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0fda5147-946f-404d-a252-e5a658c4cda5)

1.5. Создайте неиерархические категории с использованием графической утилиты «Политика безопасности».

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5d2e7728-0999-492a-a163-7135dda74aae)

1.6. Измените набор неиерархических категорий с использованием графической утилиты «Политика безопасности», для этого выполните следующие действия в разделе «Категории»:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/29a3503a-eb59-4a9d-92ad-88ed8358d193)

1.7. Измените мандатный уровень доступа с использованием графической утилиты «Политика безопасности»:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b7928f6c-9e63-434b-9be6-6bdbaacc966a)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/c8067338-1822-47e9-95ea-3a4bb7b5731a)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/35bb6514-8f3d-4657-b1b1-351b407c2cdd)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/81537da2-7808-4ba8-9864-a886ed2ade50)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ccb6ee06-f338-4f0e-bc53-918d5c8b9a23)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a19009b0-9dfa-4467-9577-3bccca0b23b5)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0d15235d-7c07-4328-9436-b2c07d384439)

1.8. Создайте общий каталог для работы от имени учётных записей пользователей user1, user2, rukoffice1 в каталоге /home/work. При этом, для работы от имени учётных записей пользователей с наборами неиерархическими категорий равными «Отдел_1», «Отдел_2» и «Управление» выделить отдельные каталоги «otdel1», «otdel2» и «upr», соответственно. При этом обеспечить хранение файлов с различными уровнями конфиденциальности в каталогах с использованием специального атрибута CCNR:

 не доделал







