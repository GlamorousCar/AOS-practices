### Параметры настройки локальной политики безопасности ОССН. Работа с учётными записями пользователей и группами



##### 1. Локальные политики безопасности и работа с учетными записями пользователей и группами

1.1. Войдите в ОССН с вашей учётной записью пользователя (Уровень_0, «Высокий»). Запустите графическую утилиту редактирования учётных записей пользователей «Политика безопасности» через меню «Панель управления» главного пользовательского меню.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5cc0a682-cf7a-4573-b0d3-ed567f1acf62)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/046fc9fa-f103-4eeb-9148-838c9614a2d3)

1.2. Откройте раздел настройки локальных пользователей, и для созданных учётных записей пользователей user1, user2, user3, user4 произвольно задайте их параметры:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/85c6ee9e-45b5-4f58-9d3f-1f9f7eb693cf)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/adb2967e-689b-46fd-92f1-9e06fc96df79)

1.3. Настройте параметры учётной записи пользователя user2:
- установить минимальное количество дней между сменой пароля – 180 дней, число дней до выдачи предупреждения о смене пароля – 5 дней;

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9511ef2d-80d9-4943-ab60-d15c04429129)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1e673a70-2363-4793-aeef-e45acae17901)

1.4. Войдите в ОССН с учётной записью пользователя user2, выбрав уровень доступа «Уровень_1». Проверьте возможность выбора набора неиерархических категорий и уровня целостности. 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/35f81f90-e95b-4001-b80d-ef795e5fb3ba)

1.5. Создайте в каталоге «Документы» файл 1.txt. Выйдите из ОССН. Войдите в ОССН с учётной записью пользователя user2, выбрав уровень доступа «Уровень_2». Создайте в каталоге «Документы» файл 2.txt.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/3d16c529-297b-4ab0-91bc-379665c63c03)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/d3b8a88f-dc6a-43bc-a7b0-5ce47fba0757)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/adedc8cc-9013-43b1-982f-96d1ced165d6)

1.6. Проверьте возможность чтения объектов файловой системы ОССН, владельцем которых является учётная запись пользователя user2 (на текущем уровня доступа «Уровень_2»):

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/62f024c1-7b8a-408a-9829-a35389ea4a31)

1.7. Проверьте наличие и возможность чтения объектов файловой системы ОССН, владельцем которых является учётная запись пользователя user2 на текущем уровня доступа («Уровень_1»):

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a249ab53-bbe9-4cd9-ab0d-e0a2e050cba7)


1.8. Войдите в ОССН с учётной записью администратора (вашего пользователя). Запустить графическую утилиту «Политика безопасности». Сравнить списки вторичных групп для учётных записей пользователей {учетная запись администратора}, user1, user2, user3, user4

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/578dfc91-1371-430c-8d35-a2eea6302dd7)

1.9. Создайте новую учётную запись пользователя user10, при этом:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/37b8f3f5-4ac1-4b3d-b5a4-3c8d29d51807)

1.10. Войдите в ОССН с учётной записью пользователя user10 (уровень доступа – «Уровень_0», уровень целостности «Высокий»). Проверить возможность создания новой учётной записи пользователя user11 с использованием графической утилиты fly-admin-smc без использования и с использованием команды sudo. Выйти из ОССН.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/28039cc5-2d69-4818-9995-fbb729c69061)

1.11. Войдите в ОССН с учётной записью пользователя user1 с уровнем доступа – «Уровень_0». Осуществить попытки запуска графической утилиты «Политика безопасности» через главное пользовательское меню и запуска её с использованием терминала Fly командой fly-admin-smc. Проанализировать результаты и предупреждения ОССН.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e9f33505-7309-426c-9d40-e86729a4ef96)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/94cdb513-8ee7-428d-bb3b-d409632f6ce3)

1.12. Осуществите переключение между сеансами различных учётных записей пользователей без выхода из ОССН:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e34609e9-68f4-4d50-8524-6ed1f2d11d87)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ed1e1ece-5d15-4174-9925-fc7d58b58a38)


1.13. С использованием графической утилиты «Политика безопасности» заблокируйте пароль учётной записи пользователя user1. Проверьте изменения файлов /etc/passwd и /etc/shadow.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/64d8cc2c-d416-474e-922c-854a34ed79b6)


1.14. Проверьте функционирование блокировки путём осуществления попытки входа в ОССН в отдельном сеансе от имени учётной записи пользователя user1. Далее снимите блокировку (выполнить удаление пароля и блокировки входа, задать повторно пароль) и проверьте возможность входа в ОССН с учётной записью пользователя user1. Для этого сначала перейти в администратора через смену сессии.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/05828003-3be3-46db-b61c-c26e82f60c86)


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a5abd77c-7537-4e73-921c-8f4822f316f8)

1.15. Выполните удаление учётных записей пользователей:
- удалить учётную запись пользователя user10 с использованием графической утилиты «Политика безопасности»;

  ![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/c1f4e606-222f-4cd8-8c53-ca7a24ac96e4)


- удалить учётную запись пользователя user2 командой sudo deluser user2;

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/08236a4f-600d-4640-8014-2e247815fd07)

- удалить учётную запись пользователя user1 командой sudo userdel user1;

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/88159df4-4c0c-4cf6-928c-6915ab6f7244)


- проверить наличие домашних каталогов учётных записей пользователей user1 и user2, после чего с использованием справочной информации по команде userdel определить её параметры, позволяющие удалять содержимое домашнего каталога учётной записи пользователя;
- удалить домашние каталоги учётных записей пользователей user1 и user2 непосредственно командами rm -r /home/userone и rm -r /home/usertwo, осуществив попытки удаления без использования и с использованием команды sudo;
- проверить наличие домашних каталогов учётных записей пользователей user1, user2 и user10 в каталоге /home/.pdp.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/33757a15-5cbd-4429-a999-a758fd0b102f)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/effc3478-42a8-43d3-b9ac-aaef337736d2)

1.16. Создайте новые группу group3 (с использованием графической утилиты «Политика безопасности») и группу group4 (командой sudo addgroup group4, выполненной в терминале Fly).

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/aa2d571b-cfd0-47be-8272-af9c66941f05)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/eeddb88d-44d5-425f-a59b-3d842f7e4399)

1.17. Добавьте учётную запись пользователя user3 во вторичную группу group3 командой usermod -aG group3 user3 и во вторичную группу group4 с помощью графической утилиты «Политика безопасности». 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/306b0acf-0cec-4035-99b7-3142a72b820d)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f74e770a-7ce4-41c0-860c-c8eb6d4f443d)

1.18. Проверьте включение учётной записи пользователя user3 в группы group3 и group4 путем просмотра содержимого файла /etc/group командами:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7cb06dea-e07d-4bb8-86e7-ac495dfd0af8)

1.19. Выполните удаление учётной записи пользователя user3 из группы group3 с использованием графической утилиты «Политика безопасности» и из группы group4 командой gpasswd -d user3 group4.


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/306c68ea-7769-4883-a3c3-695a31831d1f)


1.20. Удалите группу group3 командой sudo delgroup group3 в терминале Fly и группу group4 с помощью графической утилиты «Политика безопасности».

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0104a991-e4f0-4955-bd00-c840941e450f)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0da72999-13ca-4507-93c6-cb2999615a16)

1.21. Изучите порядок хранения параметров мандатного управления доступом и мандатного контроля целостности для учётных записей пользователей. Для этого выполнить следующие действия:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b6eb50e6-576f-4d08-b2aa-cfb3c388aad2)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/180bce28-77d0-48e2-9748-cfc4b454309f)


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f770e608-3840-481b-896e-0af17bdb9857)















