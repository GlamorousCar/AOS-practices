![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/8f2c7c9b-e70d-44f7-b4e1-bb9427918af6)### Сетевое взаимодействие в ОССН


###### 1. Настройка VPN

1.1. На машину server1 установите графический инструмент fly-admin-openvpn-server. Далее перейдите в "Пуск"  "Панель управления"  "Сеть"  "Настройка OpenVPN сервера".

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/73dd6af7-3a69-42c5-9a50-3e6932f3d60d)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/d7d83a0b-c687-4a79-8245-9ac4c96f4d8d)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/98c5c550-64af-4ddd-9535-ae991d0e5577)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/356b43b3-fc5c-4540-bb50-eeb29b7e01cf)


1.2. Настройку клиентов можно выполнить с помощью штатного предустановленного графического менеджера сетевых соединений.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6cbf512f-cd48-4115-a159-a117e5e97274)

1.3. При первом запуске графического инструмента fly-admin-openvpn-server будет создана конфигурация по умолчанию, и будут выпущены сертификаты сервера.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/99280ae1-b34b-477a-a8cb-ace9e405d4ca)

1.4. После создания конфигурации по умолчанию, пользователю станет доступно основное окно программы, которое включает две вкладки: «Настройки» и «Клиентские сертификаты», кнопки «Запустить», «Остановить», и текстовое поле для вывода сообщений.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ab071c6b-2f5f-4dbd-bc33-ca4f544e3613)

##### 2. Управление сертификатами 

2.1. Создание сертификатов
Для создания ключа и сертификата пользователя используется кнопка «Создать сертификат».

Клиентские сертификаты
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/93ddfc67-f5f5-4b2a-888d-ae00bc1349a3)

2.3. Далее на клиенте откройте сетевые соединения, нажмите на + для добавления нового сетевого соединения (тип – OpenVPN).

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2283aae8-ee72-4123-9593-7d300e761afa)

2.4. Во вкладке «Аутентификация» выберите соответствующие сертификаты. Шлюз – 192.168.1.10.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6e64bbef-a0f5-4f3b-a03e-2457231c3aed)

2.5. Нажмите на кнопку «Дополнительно». Во вкладке «Общие» выбрать «Использовать соединение TCP».
 
 ![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2a41ca02-628a-4c33-84b4-e6c59db09042)

2.7. Перезапустите VPN-сервер.

sudo systemctl restart openvpn

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7e628615-16bd-4d23-8b47-bf23ab00e03b)

2.8. Перейдите на клиента и запустите VPN-соединение 1.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1399cfa1-8863-4547-8ff5-0d648292f716)


2.9. Отзыв сертификатов.

При использовании центра сертификации, созданного с помощью инструмента fly-admin-openvpn-server, поддерживается отзыв клиентских сертификатов.
Отзыв сертификатов применяется для запрета подключений клиента, даже тогда, когда в распоряжении клиента имеются копии всех сертификатов и ключей.
Для отзыва сертификата выберите в таблице клиентов строку с отзываемым сертификатом и нажмите кнопку «Отозвать сертификат».

При выполнении этой операции:
- сертификат клиента в базе данных удостоверяющего центра будет помечен, как «отозванный»;
- будет создан (или обновлён ранее созданный) список отозванных сертификатов;
- новый список отозванных сертификатов будет скопирован в каталог /etc/openvpn/keys, и сервер openvpn будет автоматически перезапущен, чтобы обновления немедленно вошли в силу.


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/09b81911-c910-4c95-be7b-f45e5bf7d4e8)

#### 3. Диагностика работы сервиса и клиента OpenVPN

3.1. Для просмотра системного журнала можно использовать следующие команды:
journalctl просмотр всего системного журнала
journalctl -f просмотр последних событий, и вывод на экран новых событий по мере их появления

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/090e063a-d2a6-4835-9033-487e0a8f96ff)

3.2. Возможен также вывод журнала на экран по мере добавления в него новых сообщений от openvpn:
sudo 
tail -f /var/log/syslog | grep ovpn-server
будет выводить только сообщения от сервиса openvpn по мере их добавления в системный журнал.


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/503eca61-949d-4929-a8c1-a7331ed92b07)



3.4. Проверка включения ГОСТ Р 34.13–2015 «Кузнечик». Отдельно использование метода защитного преобразования можно проверить командой:
grep "grasshopper-cbc" /var/log/syslog



![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b56e3698-b6b2-43f0-af1b-84e55838338c)


