Система электронной почты на базе Exim и Dovecot

Задание: 
1. Установка программного обеспечения и первоначальная настройка 
1.1. На хосте client1.astra.test установите защищенный комплекс программ электронной почты:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9d61081a-1a33-4b6f-b47d-72007c7adefd)

1.2. Произвести первоначальную настройку exim4.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/da666b39-9957-4749-a906-07df38ade372)


1.3. Введите следующие ответы на вопросы во время первоначальной настройки (результаты запомнятся в файле /etc/exim4/update-exim4.conf.conf):
1) Тип почтовой конфигурации: доставка только локальной почты; доступа к сети нет
2) Почтовое имя системы: astra.test
3) IP адреса, с которых ожидаются входящие SMTP соединения: пусто
4) Места назначения, для которых должна приниматься почта: astra.test
5) Домены для релейной передачи почты: пусто
6) Хосты для релейной передачи почты: 192.168.1.0/24
7) Сокращать количество DNS-запросов: нет
8) Метод доставки локальной почты: Maildir формат в /var/mail
9) Разделить конфигурацию на маленькие файлы: да

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/da666b39-9957-4749-a906-07df38ade372)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/c48938b4-faa6-490e-af5a-eb9b1abec356)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1c017d1c-99f6-4892-94bd-32320422b3f4)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0a1cefa2-58fd-4c42-99d3-ca854c599352)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9a4bbb08-521d-451f-bab4-5f9adbfd493e)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/cd94b58c-0741-4637-95c9-fac09124c9e9)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5611fd54-c4f2-467e-a600-3a50a88cf13e)

1.4. Добавьте ресурсную запись MX во FreeIPA (Сетевые службы  DNS  Зоны DNS). Нажать astra.test на и выбрать «Добавить»:
1) Имя записи: @
2) Тип записи: MX
3) Preference: 10
4) Exchanger: client1.astra.test

1.5. Добавьте ресурсную запись PTR во FreeIPA (Сетевые службы  DNS  Зоны DNS). Нажать на 1.168.192.in-addr.arpa и выбрать «Добавить»:
1) Имя записи: 200
2) Тип записи: PTR
3) Hostname: client1.astra.test

1.6. Зарегистрируйте службу в домене FreeIPA (Идентификация  Службы  +Добавить).
1) Служба: imap / Имя узла: client1.astra.test
2) Служба: smtp / Имя узла: client1.astra.test
или
kinit admin
ipa service-add imap/client1.astra.test@ASTRA.TEST
ipa service-add smtp/client1.astra.test@ASTRA.TEST

1.7. Создайте ключи для почтовых служб.
1) создать ключи для служб imap (dovecot) и smtp (exim4) и добавить их в keytab-файл:

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/3b2d0bbd-fcea-4e4b-8f9a-6cd29a25b83e)

sudo ipa-getkeytab -p imap/client1.astra.test@ASTRA.TEST \
-k /var/lib/dovecot/dovecot.keytab
sudo ipa-getkeytab -p smtp/client1.astra.test@ASTRA.TEST \
-k /var/lib/dovecot/dovecot.keytab
2) назначить права доступа к keytab-файлу для пользователя dovecot: 
sudo setfacl -m u:dovecot:x /var/lib/dovecot
sudo setfacl -m u:dovecot:r /var/lib/dovecot/dovecot.keytab

1.8. В файле /etc/dovecot/conf.d/10-master.conf в секции service auth добавить:
unix_listener auth-client {
	mode = 0600
	user = Debian-exim
}

1.9. Добавьте права доступа к каталогу /var/spool/exim4.
sudo chown -R Debian-exim:Debian-exim /var/spool/exim4/
Примечание: при возникновении ошибок доступа можно попробовать установить полные права на /var/mail. 

1.10. Настройте аутентификацию через Kerberos в файле /etc/dovecot/conf.d/10-auth.conf.
### верх файла
disable_plaintext_auth = yes

### середина файла
auth_gssapi_hostname = client1.astra.test
auth_krb5_keytab = /var/lib/dovecot/dovecot.keytab
auth_mechanisms = gssapi
auth_realms = astra.test
auth_default_realm = astra.test
#auth_mechanisms = plain

### конец файла
!include auth-system.conf.ext

userdb {
 driver = static
 args = uid=dovecot gid=dovecot home=/var/spool/mail/%u
}

1.11. Внесите соответствующую конфигурацию в файл /etc/dovecot/dovecot.conf (проверить, что присутствуют данные настройки).
!include_try /usr/share/dovecot/protocols.d/*.protocol
protocols = imap

listen = 192.168.1.200

dict {
}
!include conf.d/*.conf
!include_try local.conf

1.12. Внесите соответствующую конфигурацию в файл /etc/dovecot/conf.d/10-ssl.conf (проверить, что присутствуют данные настройки).
ssl = no
ssl_cert = </etc/dovecot/private/dovecot.pem
ssl_key = </etc/dovecot/private/dovecot.key

1.13. Перезапустите службу Dovecot.
sudo systemctl restart dovecot

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9ff1d13a-bd55-4094-99ec-a49d38c117d8)


1.14. Настройте аутентификацию через Kerberos для Exim в файле /etc/exim4/conf.d/auth/33_exim4-dovecot-kerberos-ipa.
dovecot_gssapi:
driver = dovecot
public_name = GSSAPI
server_socket = /var/run/dovecot/auth-client
server_set_id = $auth1

1.15. Перезапустите службу Exim и добавьте ее в автозагрузку.
sudo systemctl restart exim4

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a7a68a3c-f3ec-40bb-a627-15f4f2e1e350)

sudo systemctl enable exim4

1.16. Отключите настройки фаервола (при возникновении ошибок в разрешении имен).
sudo systemctl stop ufw

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/498615bc-65cd-4fb5-a254-033e6001f12f)


1.17. Добавьте рекурсивные права доступа к директории /var.
sudo chmod -R 777 /var

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/18242a74-5218-4328-a96d-c4f05d6bc7c4)

2. Настройка почтового клиента «Почта Thunderbird»
Предварительно: для настройки почтового клиента Thunderbird следует:
- зайти под доменной учетной записью в систему;
- запустить программу Mozilla Thunderbird (Пуск→Сеть);
- в появившемся окне «Настройка имеющейся у вас учетной записи электронной почты» ввести адрес электронной почты в поле «Адрес эл. почты:» и нажать кнопку «Настроить вручную...»;
- в этом же окне настройки учетной записи должны появиться новые поля для ввода. В полях «Имя сервера» для входящей и исходящей почты ввести DNS-имя почтового сервера и нажать кнопку «Перетестировать»;
- в случае, если перетестирование пройдет успешно и в полях «Аутентификация» будут определены значения «Kerberos/GSSAPI», нажать кнопку «Готово».
Настройка почтового клиента Thunderbird должна быть произведена на всех комбинациях уровней конфиденциальности и категорий.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/bf6e8164-dffc-4256-aee3-d7131198520b)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1783ca3c-3b7a-4d3b-8740-39f3bdae0e00)

2.1. Зайдите на хосте server1.astra.test под доменной учетной записью ipauser2 с разными уровнями конфиденциальности: 0, 1 и 2.

2.2. Настройте почтовый клиент «Почта Thunderbird» для учетной записи ipauser2 на каждом уровне конфиденциальности и отправьте письма пользователю ipauser1.

2.3. Зайдите на хосте server1.astra.test под доменной учетной записью ipauser1 с разными уровнями конфиденциальности: 0 и 1.

2.4. Настройте почтовый клиент «Почта Thunderbird» для учетной записи ipauser1 на каждом уровне конфиденциальности и прочитайте полученные письма.

Пример того, как должна отображаться почта.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/4873f0e0-bc46-405b-a03d-0ddeed636b05)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0436459d-eae7-4c03-901d-bbf5e6b1a1a5)



