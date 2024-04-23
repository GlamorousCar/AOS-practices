### Настройка сети в Astra Linux

##### Задание 0. 

Так как работа с ВМ проходит внутри гипервизора, а не virtualBox , у меня нет возможности 
продемонстрировать данные варинаты настройки сети

##### Задание 1.

1.1 Определить сетевые параметры, полученные автоматически по протоколу DHCP.
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/4acd334c-652d-474a-b9a7-037013a48309)

1.2 Отобразите таблицу маршрутизации.
Так как сеть не настроена , маршрутов нет

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/724c0058-802b-4443-8feb-46fd51d39159)

1.3. Посмотрите содержимое файла /etc/resolv.conf. С помощью какой службы была сгенерирована информация об адресе DNS-сервера
Указан IP сервера dns который указывался при установке

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b3cd21f5-29df-460e-a2da-8efc19a54b62)

 1.4. Посмотрите содержимое файла /etc/hosts.  Отправьте эхо-запрос на доменные имена из данного файла.
 
 ![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e6341a13-ae98-43ba-9f43-450225af7b33)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a0b04bfb-3bdb-4649-a1fb-8a22f0278fcf)

##### 2. Служба NetworkManager

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/8dbc3fcd-d50f-4be1-b47a-2b13eff5a865)

2.2. C помощью утилиты nmcli задайте статический IP-адрес для интерфейса eth1, адрес шлюза по умолчанию и адрес DNS-сервера

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2a0d970e-bffb-4673-8166-e93b711a78fb)

2.3. Отобразите содержимое файла конфигурации «Проводное соединение 1».

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/03aa34d3-ce46-4647-8407-ebafdc1f7ca9)

2.4 Нет возможности выполнить. так как не установлен графической интерфейс fly

##### 3. Служба networking
3.1. В конфигурационном файле NetworkNamager.conf укажите параметр [ifupdown] managed=true, а также остановите службу NetworkManager.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b6e0d07b-c568-4e4f-9818-6bc62aca6157)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5cfcf9b4-f153-49f9-be72-49599cfa9953)

3.2. В конфигурационном файле /etc/network/interfaces задайте статические настройки для eth1. Перезапустите службу networking.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ce77174c-ccc9-4b97-bd88-661ae56e7f3a)

3.3. Для проверки отправьте эхо-запрос на адрес шлюза по умолчанию.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a3531abf-8175-4f30-9bbd-c0d9a6898cc0)

 ![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/3c05110e-21ad-4478-bae7-58040528533c)


##### 4. Временное задание IP-адресов

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2a0f47d2-8869-443d-a361-58666602c766)

4.2. Задайте интерфейсу eth1 IP-адрес из той же подсети, в которой он сейчас находится.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1d5ff091-9af1-4a26-b73a-54016b4681c7)

4.3. Добавьте адрес шлюза по умолчанию.
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7e554aca-d63e-4d1c-be8f-f1ccf67ca85a)


##### 5. Утилиты для проверки настроек сети

5.1. Отправьте эхо-запрос за какой-нибудь адрес в интернете (используйте IP-адрес и доменное имя).

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a2cc28ec-abcf-439d-85ad-d4480be3ad38)

5.2. Сделайте трассировку для адреса 8.8.8.8 и ya.ru.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/54d89682-b3f9-4e69-bfd7-2f4c52043758)

5.3. Запустите утилиту nslookup, которая предоставляет интерфейс командной строки для обращения к системе DNS. 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/d0a7a03e-224d-43b2-a40e-e226f98e08c8)


5.4. Воспользуйтесь утилитой dig для просмотра информации о преобразовании доменных имен в IP-адреса для dns.google.
dig dns.google

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1398e3b8-4001-49b2-b75f-fbebcb7e83fb)

