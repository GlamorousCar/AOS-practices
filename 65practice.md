Практическая работа № 5. Система управления идентичностью (IdM) – FreeIPA

0. Подготовка сервера и клиента

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f40af4bf-8f07-4f17-bed2-b78416663dee)


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0e0cccca-ca6c-400c-8335-47dcbc6f8e63)


1.1. Установите серверное и клиентское программное обеспечение FreeIPA на server1.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/cd8c4625-7647-493f-a24c-d17d81d79450)

1.2. Запустите сервер FreeIPA (выбрать сетевой интерфейс из внутренней сети и задать пароль для доменной учетной записи admin). Далее перезагрузите ВМ.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/c393b266-9368-4f8c-9053-78b58305d3c5)

1.3. Проверьте статус служб FreeIPA командой ipactl.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/92c9e99f-1b4d-48b2-9417-73a933b32ce4)

1.4. Проверьте доступность административной веб-консоли FreeIPA через браузер Firefox (пользователь: admin, пароль был введен во время запуска сервера FreeIPA)


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/39be7d24-762b-4a85-97c9-4a1187452d2e)

2. Установка клиента и ввод клиента в домен
2.1. Установите клиентское программное обеспечение FreeIPA на client1.
sudo apt install fly-admin-freeipa-client


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/352cdb3b-0515-42ba-a212-68a7047ef8b3)

2.2. Запустите клиент FreeIPA и перезапустите ВМ.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/60cb36d1-972b-4254-9c50-d6288f9d10b0)


3. Управление учетными записями пользователей
3.1. Создайте учетную запись доменного пользователя ipauser1 из веб-консоли (мин. уровень конфиденциальности – 0, макс. – 1):
Идентификация→Пользователи →+Добавить (заполнить обязательные поля и задать пароль).


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/fc8c203e-399b-4381-b978-3e781c0ffef3)

3.2. Создайте учетную запись пользователя ipauser2 и задайте пароль из командной строки с помощью утилиты ipa (мин. уровень конфиденциальности – 0, макс. – 2).

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/66389251-ec8c-4e1a-9a5f-cdba5c309c55)

4. Управление доступом на основе узла
Выполняется с помощью утилиты ipa в командной строке на сервере FreeIPA (может быть также выполнено в веб-консоли).
4.1. Просмотрите информацию о всех настроенных службах из командной строки и проверьте, есть ли в списке служба fly-dm.
kinit admin

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/51cfeae9-88fa-46aa-b321-351c1a916190)

ipa hbacsvc-find --all

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/fc7d3c8a-cfef-4cb7-9c10-3d91e1518db3)

4.2. Создайте правило, которое разрешает доменному пользователю ipauser2 графический вход в систему на хосте client1.astra.test:
1) На сервере FreeIPA добавьте службу fly-dm.
ipa hbacsvc-add fly-dm --desc="Fly Display Manager"
2) Создайте «пустое» правило с именем flydm.
ipa hbacrule-add flydm
3) Добавьте в правило flydm учетную запись пользователя ipauser2.
ipa hbacrule-add-user flydm --users=ipauser2
4) Добавьте в правило flydm хост client1.astra.test.
ipa hbacrule-add-host flydm --hosts=client1.astra.test
5) Добавьте в правило flydm службу fly-dm.
ipa hbacrule-add-service flydm --hbacsvcs=fly-dm

4.3. Просмотрите правило flydm.
ipa hbacrule-show flydm


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e15c2513-b659-4a07-9f9e-43057994fa53)


4.4. Протестируйте правило flydm для пользователей ipauser1 и ipauser2 с помощью утилиты ipa hbactest.
ipa hbactest --user=ipauser1 --host=client1.astra.test --service=fly-dm
ipa hbactest --user=ipauser2 --host=client1.astra.test --service=fly-dm

4.5. Отключите правило allow_all и снова протестировать правило flydm.
ipa hbacrule-disable allow_all
ipa hbactest --user=ipauser2 --host=client1.astra.test --service=fly-dm
ipa hbactest --user=ipauser1 --host=client1.astra.test --service=fly-dm

4.6. Зайдите под учетными записями ipauser1 и ipauser2 на хостах client1.astra.test через графический вход. 

4.7. Попробуйте зайти пользователем ipauser2 в client1.astra.test через виртуальный терминал (вход не должен быть разрешен).

4.8. Включите правило allow_all.
ipa hbacrule-enable allow_all

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/c88c4229-478f-4b8e-a337-731759698797)






