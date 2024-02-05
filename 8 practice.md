### Процесс загрузки и выключения системы

Перезагрузим систему и нажмем клавишу e для перехода в загрузчик GRUB

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9bcf0cb3-2af6-4097-b398-04c1a51c3fdc)

Наждем c для перехода в grub shell

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9a9f2b46-c88f-46d8-9f5a-f3402ae7acb6)

Выполним перезагрузку еще раз и войдем в GRUB shell. Посмотрим список команд и содержимое. Далее сымитируем загрузку ядра и образа.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/69e5e803-ae68-4962-83c2-e97e6abfce71)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6c4bd460-e234-42e8-b1d1-17dd86d2cdb6)

Изучим содержимое конфигурационного файла загрузчика GRUB

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6e0bfff9-a78b-4eb6-b8f2-63d4931de9b2)

Отобразим содержимое файла /etc/default/grub

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/22aba34a-17a0-4f0b-acd5-766bf9dadcac)

Изменим время ожидания загрузчика, установим значение 10 секунд и включим параметр загрузки splash

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6a1cdd98-3d86-472d-baac-e5b5732c4e75)

##### Управление службами с помощью systemd

Просмотрим все юниты, которые есть в системе.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b82bfd11-9b8c-45af-a335-ee9ff658211e)

Просмотрите все юниты, которые относятся к типу target.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/60037ac8-cb02-4ed3-ad05-048e2f28c874)

Отобразим статус сетевой службы NetworkManager и проанализируем содержимое вывода.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/acc83009-c7c2-49c1-8ed2-b9bffdc420db)

Служба запущена

Отобразим содержимое юнита, с которым связана служба NetworkManager.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/62cd3e06-8c95-4f02-8cfa-2bebb773bcca)

#### Юниты systemd типа target

Объединим службы ssh и networking.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5f8b68bb-9ae2-414e-8197-114bcd8fb17c)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/fca5ddcd-0cad-4898-8574-64cf9ab8156a)

запустим созданный ssh-networking.target. 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b2b19152-80b6-409a-b6a1-c1a76d0a3531)

#### Загрузочные таргеты

Посмотрим список существующих загрузочных таргетов.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7467740a-4949-4ce9-b76f-9e14621690c1)

Перезагрузим систему с использованием таргета reboot.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b6af7b18-8df6-4eee-b9f6-f957ccd1eee5)


Просмотрим, на что ссылается таргет по умолчанию

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/14d5b7a1-5e62-428b-9326-089590522bbe)

Отобразим содержание юнита для default.target и проанализируем содержимое.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/dc68d117-da65-4a9d-888f-14176c030e21)

### Управление модулями ядра

Посмотрим все загруженные модули ядра

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0a5be2af-f835-4437-950a-13a35146a242)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5d593003-0da3-4410-8baf-1345c0aed4ba)

Отобразим список доступных сетевых карт.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7236fa62-514f-45b9-be81-07ef75f924f7)

Просмотрим информацию о драйвере e100 и загрузите его. 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f0958f06-9a6a-4393-bc68-205f7a787ed3)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/03fda4b1-4c1d-4d6a-9601-41463a2596ab)

Добавим в /etc/modules информацию о том, что будет использоваться новый драйвер. Обновим файл initramfs после внесенных изменений.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/64fce826-ec24-43de-b1d2-e945a27b9534)

Посмотрим параметры ядра. Далее отобразим значение параметра ip_forward. 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/31944ca5-935a-42da-9585-366616c8d176)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/91761c1a-4023-4403-84c6-2c88c7f68e3c)

#### Управление устройствами

Отобразим информацию о разделе диска /dev/sda1

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5ba1ee8e-35e9-45c2-b219-b922fd03b52e)

Отобразим информацию о всех родительских устройствах для /dev/sda1.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/80d7730d-0f89-4b64-8adf-24596524e9a2)

Ознакомися с графическим интерфейсом для менеджера устройств

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/4133f6d0-4f0c-4397-ae0e-f3fcb14a338c)

Узнаем, какие устройства подключены к шине PCI, а также параметры CPU и оперативной памяти.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6125db91-ae06-4c4c-8ddc-4e5b61bd16ea)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2f432840-1fb9-4e7f-9367-87096beacee4)

#### Управление программным обеспечением

Посмотрите, какие пакеты установлены в системе и посчитайте их количество.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/014778c7-c58a-4ff2-9246-eaac53e2b9db)

Узнаем информацию о пакете командного интерпретатора. Найдем все файлы, которые связаны с этим пакетом.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/09328dce-9024-43aa-929f-099cea04dcc9)

Отобразим информацию о репозиториях, доступных системе

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ee7293e2-4289-4102-8476-83357ed8d64b)

Установим пакеты ssh, isc-dhcp-server, bind9, apache2

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a17bfe23-d7eb-465b-94cc-87ee10b83208)

##### Дополнительно

Утилита aptitude

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2e1427f5-e666-4e5a-bd44-03a1757e5146)

Программа synaptic

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/cd66511f-f49f-40ce-a021-cdd7fd70f00e)















