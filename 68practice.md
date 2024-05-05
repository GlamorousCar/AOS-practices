![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ba0be4d4-e8da-442c-9b66-5846e255f473)Практическая работа № 8. Установка Astra Linux по сети

1. Установка и настройка DHCP/TFTP-сервера
Предварительно: вызовите программу synaptic, подключите все возможные репозитории и введите команду sudo apt update.

1.1. На client1 установите необходимые пакеты:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/015548f3-0cda-4647-8a43-643ca201ecf8)

1.2. Настройте конфигурацию в файле /etc/dhcp/dhcpd.conf. В данной конфигурации dhcp сервер будет определять тип клиента (UEFI или Legacy BIOS) и передавать ему нужный загрузчик. Конфигурация представлена далее и может быть скачена по ссылке: https://cloud.mirea.ru/index.php/s/gDdHtJBFm8aqdew

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/cc6b10ad-5daa-4ba1-82fd-393f6b2ecdb9)

1.3. В файле /etc/default/isc-dhcp-server добавить конфигурацию.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a25b59af-4e5b-4c8f-a167-058b206b7a1c)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a8f37828-dc37-47a4-ae02-e88db3b487f4)

1.4. Установите ftp сервер.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/91b54f0b-936d-431d-aeb9-a9b235b4d99e)

1.5. В конфигурационный файл /etc/vsftpd.conf внесите следующие данные:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/bd41b9af-6636-4043-820f-46592bb2026c)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1a5eede2-8555-4ea6-b00e-c72e164a7cd9)

1.6. Перезапустить сервис ftp.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1fd64cc2-a057-42f5-b235-44e271784a1f)

1.7. Скопируйте необходимые файлы для установки. Независимо от использующейся службы DHCP для загрузки по сети нужны следующие файлы:
Эти файлы находятся на установочном диске в каталоге netinst и для того, чтобы они могли быть переданы клиентам, они должны быть скопированы в каталог /srv/tftp/. Предполагается, что основной установочный диск находится в приводе компакт дисков.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5933ba7b-e7e8-4654-b294-735791fc914b)

1.8. Скопирутйе в каталог /srv/tftp файл pxelinux.0 и необходимые библиотеки syslinux из установленной ОС

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9381045e-cd5f-48be-9761-be64a1e10a3f)

1.9. Создать каталог /srv/tftp/pxelinux.cfg/.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7dd6ead5-8674-40ff-af5b-2848430771d4)

1.10. Создать в этом каталоге файл /srv/tftp/pxelinux.cfg/default с содержимым, которые можно скачать по ссылке: http://cloud.mirea.ru/index.php/s/k2qYG9SqHp7aN8e

1.11. Для загрузки в режиме UEFI служит специальный EFI образ загрузчика grub. Для его установки:
1) Загрузите архив с образом с помощью web-браузера по ссылке: https://nextcloud.astralinux.ru/s/AfHKawSywceJ2df. По умолчанию архив будет сохранен в подкаталоге Загрузки домашнего каталога;
2) Распакуйте архив Загрузки/netinst.tar.gz в каталог 




