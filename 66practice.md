![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/37522e6a-7433-42f2-8fc8-6bf24070742a)1. Установка и настройка веб-сервера и виртуального хостинга с помощью Apache2
1.1. Установите apache2 на client1.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/d75c3e15-5b28-4e99-bd61-496759d5c4b1)

1.2. Выключите режим AstraMode в /etc/apache2/apache2.conf.
AstraMode off

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/3d1ac85b-d797-4594-9dfa-35d81ddbe5af)

1.3. Перечитайте конфигурацию веб-сервера и проверьте его состояние.
sudo systemctl reload apache2
sudo systemctl status apache2


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f7ab535d-fcca-4b15-8926-1eac44154b46)

1.4. Создайте файл конфигурации виртуального хоста в /etc/apache2/sites-available.


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a487ca4c-8936-4496-b196-867afe5a6522)

1.5. Отредактируйте файл конфигурации виртуального хоста, указав доменное имя сервера в параметре ServerName и путь к каталогу с веб-страницами.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5f2e16cc-3de9-438e-a354-c05803049cb6)

1.6. Создайте каталог для размещения веб-страниц.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/256f8f81-2bd7-48e8-8499-ee2a2727bdb3)

1.7. Разместите в созданном каталоге веб-страницу index.html со следующим содержимым:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/628056b3-bdf8-4719-a613-18ce9d9c9973)


1.8. Активируйте сайт, описанный в конфигурации виртуального хоста, и перечитайте конфигурацию веб-сервера.


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b3f9faac-df15-424d-a1bf-2c4569e29528)


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/81bb4466-144f-4fc6-b3d4-c45cacee2c86)

1.9. Проверите созданную страницу в браузере (зайти на 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b1f377f3-d7ea-4037-9dce-e5f19d00daf6)

2. Настройка Kerberos авторизации веб-сервера Apache в домене FreeIPA
2.1. На client1 установить модуль авторизации через Kerberos.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/216e4582-74f3-4952-a879-3fc1f6549e78)

2.2. На client1 зарегистрировать веб-службу web.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b48aa56a-8250-40ef-a440-7671152b95bc)

2.3. На client1 создать ключи и сохранить их в файле /etc/apache2/keytab. 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/201dc358-166c-404f-b604-04c41d4155c3)

2.4. Установить права и владельца на файл keytab.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/8d5aac09-ade1-47d4-bf71-0a4ba8f4a27e)

2.5. Настроить Kerberos авторизацию на веб-сервере, включив секцию <Directory> в настройку виртуального хоста внутри секции <VirtualHost> (файл client1.conf).

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0383cd6c-dd97-4132-8be1-543d2ab75ac5)

2.6. Перезапустить веб-сервер.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/210d6fe0-6ad8-44f9-a242-ce927659ba5d)


3. Создание страниц с разными уровнями конфиденциальности на ВМ client1

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/911563dd-ccfb-458c-b7c5-74e944773dbe)









