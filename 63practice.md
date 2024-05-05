SQUID – кэширующий HTTP/FTP прокси-сервер

1. Установка, первоначальная настройка и диагностика SQUID
Предварительно: настройте полное доменное имя server1.astra.test на сервере SQUID и внесите следующую конфигурацию в файл /etc/hosts.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/83cdfc08-8930-484b-bad5-4e774d1dff4c)


1.1. Установите SQUID на server1.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1f51f81a-1127-4913-aa5d-a385224c78e9)

1.2. Сохранить исходный вариант конфигурационного файла SQUID.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/09e9e2a6-64dd-4c28-90ab-f503d543d1a9)

1.3. На основе исходного конфигурационного файла SQUID создайте новый конфигурационный файл, исключив комментарии и пустые строки, содержащиеся в исходном файле.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/fbe96b2c-f03d-4269-becc-0db0febbb73d)

1.4. Создайте в конфигурационном файле /etc/squid/squid.conf список управления доступом типа src с именем localnet, добавив в этот список управления доступом все хосты из сети 192.168.1.0/24.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/bbf24a59-b008-4576-bab6-b88ccee13d06)

1.5. Включите в /etc/squid/squid.conf правило, разрешающее хостам, определенным в списке управление доступом localnet, обращаться к прокси-серверу.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0a495048-798e-4337-8e36-e41169f63a04)

1.6. Выполните команду, которая позволяет перечитать измененный конфигурационный файл.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a8a3071b-9609-481b-aff3-cb20ff39c194)

1.7. Проверьте доступность сервера SQUID и возможность доступа к Интернет-ресурсам на ВМ server1 (используйте браузер Firefox). Зайдите в настройки браузера и выполните следующую конфигурацию:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5ee90ef8-383d-4b71-87ce-6f27deb71bde)

1.8. Просмотрите журнал для SQUID.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/aad7c587-17ba-4747-9a8f-d8022cda1c6a)


2. Настройка доступа в веб-ресурсам
2.1. Создадим список управления доступом типа dstdomain, который включает домен youtube.com. Внесите дальнейшую конфигурацию в самый верх файла /etc/squid/squid.conf.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ac89ff05-c25d-46fa-b45f-bf43aa60e531)

2.2. Создадим список управления доступом типа time, который определяет рабочее время.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/aac69e2e-4d3d-43bc-b2df-006e11aab186)

2.3. Добавьте правило, которое запрещает доступ к сайтам в домене youtube.com в рабочее время, указав одновременно оба списка управления доступом.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/df81d571-7c39-4c95-9231-62c16b240c01)

3.3. Базовая аутентификация NCSA
3.1. Установите программный пакет apache2-utils на server1.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/10156bd0-2ace-457c-9c4a-b2089ea30bf6)

3.2. Командой htpasswd создайте пользователя iuser.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/90965b25-44a1-4cdb-8ec2-ceed0de92749)

3.3. Установите владельцев proxy:proxy и права 640 на файл с паролями

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/601242e7-b8c6-4429-bb8d-6b613f496590)


3.5. Выполните перечитывание конфигурационного файла сервером SQUID.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/8c8c796e-a2ad-42ff-81a6-d79d1765bad1)









