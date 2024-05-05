1. Выделение адреса сети и хоста с использованием сетевой маски

  ![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/863164cb-f4f9-458d-b421-0aa4a7d6bd4a)



3. Настройка сетевых интерфейсов и сетевых соединений с помощью nmcli, nmtui и nm-connection-editor
2.1. Добавьте еще один сетевой адаптер с типом подключения «Внутренняя сеть». Он будет использоваться на протяжении всего сетевого курса. Отобразите настройки для сетевых соединений.
   
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/3dff4655-ea5c-441f-98c3-bee92a337a75)

2.2 C помощью утилиты nmcli задайте статический IP-адрес для интерфейса eth1, адрес шлюза по умолчанию и адрес DNS-сервера.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/d3989a06-f28d-44e3-81a5-1bf7079cb1c4)

2.3. Ознакомьтесь с изменением сетевых параметров для интерфейсов через графическое окружение (Панель управленияСетьСетевые соединения) или вызовите nm-connection-editor.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a5a2d59f-637f-445d-93e9-84a8ee21b050)

2.4. Ознакомьтесь с изменением сетевых параметров для интерфейсов через пвевдографическую утилиту nm-tui.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0b9863ac-4267-4c92-9ec3-049717225ff4)

3. Служба networking и команды ifup/ifdown

3.1. В конфигурационном файле NetworkNamager.conf укажите параметр [ifupdown] managed=true, а также остановите службу NetworkManager.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/28539c49-32fe-4fd0-8729-7e088d84e202)

3.2. В конфигурационном файле /etc/network/interfaces задайте статические настройки для eth1. Перезапустите службу networking.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2ed2a3a7-7183-4cd1-90d8-5e70696d2934)

3.3. Для проверки отправьте эхо-запрос на адрес шлюза по умолчанию.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e953246e-1da4-477b-a547-bcd5ad152fa1)

4. Статические маршруты

4.1. Просмотрите содержимое таблицы маршрутизации. Определите маршруты по умолчанию и адреса шлюзов по умолчанию

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e6e11bd6-9db7-460d-96a5-76f85168bd53)

4.2. Задайте маршрут для сети 192.168.2.0 через адрес 192.168.1.1.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/20c23b5b-2d95-4839-9ac9-6239c606fdd9)


5. Утилиты для диагностики сети
Заранее установите пакет dnsutils.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/cf8d7107-7f22-4ce5-a0d0-06c06e7fb8c0)

5.1. Отправьте эхо-запрос за какой-нибудь адрес в интернете (используйте IP-адрес и доменное имя).

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/38525fd4-f5ec-4188-9e73-73d4787a8586)

5.2. Сделайте трассировку для адреса 8.8.8.8 и ya.ru.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/cc768485-2469-4e64-b896-79061f4433ae)

5.3. Запустите утилиту nslookup, которая предоставляет интерфейс командной строки для обращения к системе DNS. 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5a3bfd17-8514-45ca-aa0b-25e4a5b01a78)

5.4. Воспользуйтесь утилитой dig для просмотра информации о преобразовании доменных имен в IP-адреса для dns.google.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/677c5ce7-b1d1-41e0-8331-8987adc95ee7)

6. Установка и настройка ведущего, подчиненного и кэширующего DNS-сервера для зон прямого и обратного отображения
6.1. Создайте клон виртуальной машины (ВМ):

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5b4b06ed-b3c8-48bf-bf1f-042b28ad1ae7)

6.2. На сервере установите пакет bind9 и измените имя хоста.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/90ae3d1f-dc0d-4a92-a278-5f4f66ac89f7)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/af4dd600-a23f-4147-9081-f7505b981a2c)

6.3. В файле /etc/hosts замените astra на server1

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/711d5f9b-628e-45bc-bebd-307cd01b0c84)

6.4. В файле /etc/bind/named.conf.options измените параметр dnssec-validation с “auto” на “no”. 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0f87599c-04bd-4b0a-87a1-85d8467fe02b)

6.5. В файле /etc/bind/named.conf.default-zones опишите прямую зону astra.test и обратную зону 1.168.192.in-addr-arpa, для которых наш сервер является ведущим сервером DNS. Исходную конфигурацию можно удалить.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2df2da4b-1bb3-4aa9-a443-7433c92e971e)

6.6. Проверьте правильность внесенных изменений в настройки сервера DNS.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6c51af9e-8f1c-4339-af01-8483f5e6cee5)

6.7. Создайте 2 файла в директории /etc/bind: db.astra.test и db.1.168.192.in-addr.arpa и скопируйте:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f7a8dc05-d1b7-4223-8b71-744adec5e300)

6.8. Отредактируйте файл прямой зоны db.astra.test:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e6bf4487-0c09-4e95-8ebb-20335613be37)

6.9. Отредактируйте файл /etc/resolv.conf.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/548a661c-3b20-4e3d-b4df-f4eeb9e8ccb0)

6.10. Перезапустите сервис bind9. Отправьте эхо-запрос для проверки записей из файла db.astra.test.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/3f0d8a36-5321-4535-b836-4911e1eb90f9)

6.11. Перейдите на клиентскую машину (клон). Задайте имя хоста client1, а также укажите IP-адрес 192.168.1.20. Далее внесите изменения в файл /etc/hosts.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a22ab1a1-1f5a-4c12-afd5-997aa86fa8ee)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/84cfa508-14be-42d2-b33e-f3da437f3cd9)

6.12. Отредактируйте файл /etc/resolv.conf. Все настройки – как в пункте 6.9.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/333bc2ca-9645-4669-b753-73f36bdab5e1)

6.13. Отправьте эхо-запрос для проверки записей из файла db.astra.test для клиента.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2a368d6d-f5eb-434f-a170-a7087e6adabc)

7. Диагностика работы службы DNS

7.1. На сервере воспользуйтесь командой nslookup со значением имени и IP-адреса клиента и сервера.

   ![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a4b13841-1fce-4fc4-8cde-e31d8a6bcfff)

8. Установка и настройка DHCP для выдачи клиентам динамических и постоянных адресов, настройка DHCP на клиентской стороне, диагностика службы

8.1. На сервере установите пакет isc-dhcp-server.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/62c8e74c-c2e6-43bc-b11e-6ecf8aacad68)

8.2. В файле /etc/default/isc-dhcp-server определите, на каком сетевом интерфейсе будет работать сервер DHCP. Запишите в этом файле следующее значение:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/be6af939-515c-4497-bd65-1616a1314716)

8.4. Запустите службу DHCP и проверьте, что служба запущена

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a2720c49-f1a2-40a7-b092-ca4d118852b1)

























