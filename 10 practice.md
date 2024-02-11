### Расширенное администрирование устройств хранения данных. Система журналирования в Astra Linux

Добавим два диска в виртуальной машине, каждый диск объемом 8 ГБ

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ddfe0916-7730-43c8-a732-6b2552540298)

Установим пакет LVM

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9176bb4c-fcb0-4d7d-b889-12dbdcefc6fa)

Создадим физические тома для двух дисков. 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1a22f631-ea26-4c13-bdd3-951883cc1658)

Просмотрим информацию и атрибуты физических томов

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f7112f2b-db77-4fdb-8454-bf85a443bf82)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ff0a07c0-87e6-42a3-8901-9a7728bc1efc)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b6b7483b-1779-491b-a163-fbf04220dca5)

Создаlbv группу томов из двух дисков

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/32cc8687-62b6-4430-8a72-925073cbf43a)

Отобразим информацию о группе томов.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9ef24d0e-a706-4f38-ba22-945197fe121c)

Создадим логические тома на 9 и 6,9 ГБ.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/48589b09-c660-4922-94dc-c816a9b9b75a)

Отобразим информацию о логических томах.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/06d18c56-74ed-4a38-86d9-a39223760ee8)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/879e0ab9-12fb-4ceb-b716-bee64da15679)

Создадим файловых систем логических томов

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e23831e0-6c18-47ef-8e4d-91c5dfe36117)

Создадим точки монтирования.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/48bd286f-4fa7-416d-b0fe-8397524f09fe)

Создадим юнит systemd для монтирования

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/c387061a-43a1-436f-8285-87aecb432367)

Активируем созданные юниты.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6b99f448-9b94-4db2-9515-88b3e7ae51c0)

Проверим файловую систему на наличие ошибок.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/10af7b69-bcec-4cb0-950e-37e094aab11c)

Уменьшим размер первого тома с 9 ГБ до 7 ГБ. Важно: сначала нужно уменьшить размер файловой системы, затем том

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/15350baa-3e64-450a-91f6-970857366863)

Заново смонтируем файловую систему.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/c230da3c-6c7e-4da6-aa3c-1461a09cf13e)

Добавим новый жесткий диск объемом 3 ГБ. Создадим физический том, добавим его в группу физических томов и увеличьте размер логического тома lv02 на 3 ГБ. Далее увеличьте файловую систему.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9e7c8690-8765-4016-938f-85a66d41e63c)

Службы журналирования

Отобразим сообщения, которые поступают в реальном времени при перезапуске службы NetworkManager.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/3847d187-f428-4700-be48-4f175811c74a)

Просмотрим сообщения об ошибках, связанные с пользователем с UID=1000.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7c40274c-0dda-4f31-9f43-61921d0a40b5)

Выведем сообщения журнала для юнита data1.mount за определенный период времени.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f3a91d45-24ed-434c-b6a8-845c247db5cd)

Просмотрим журнал предыдущей загрузки.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/531409af-dcaa-499a-b77c-4b32d0364b68)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2ecf2377-69d4-4d98-beae-d9a8cb63c3ff)

Создадим каталог для хранения журналов, установите необходимые атрибуты и перезапустите службу.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/c3f694d1-91ee-4ec3-a421-487a3ea4c0d5)

Сделаем так, чтобы journalctl показывал сообщения без прерывания строк.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5f2e48a6-1eba-450e-9e11-c41347d9d62e)






