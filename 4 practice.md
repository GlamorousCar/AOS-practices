### Произведение операций с файлами. Архивация и сжатие данных

**Цель работы**: научиться производить различные операции с файлами, изменять права доступа и атрибуты, применять архивацию и сжатие данных.

Установим утилиту `tree`
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1ceeeeca-04ac-436c-b05a-8c75360421d7)

Результат работы команды `tree`
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/1df1047c-9349-41ba-a0b6-7e2835952554)

Изменим режим доступа к файлу file1

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/17f5c395-2246-4374-8dcf-c8098f2d8e90)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0aa4825e-f0f8-4217-8c1e-4318551ab025)


![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/039637c7-3c06-4ec7-8a36-2ebb08255da2)

Изменим режим доступа к `file2`
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/01b360e8-ec9c-4837-b2f5-2d69ba0b769e)

Изменим содержимое файла `file2`
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a1be2811-309e-42fd-b296-0ebadd6fd3a3)

Пробуем запустить файлы file1 и file2

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ef9cdd7c-e1cf-45dd-9790-861041e6776a)

Как можно заметить команда внутри file2 сработала

Добавим StickyBit на директории
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/264fbd64-c645-41f1-a0b0-66797ab6cb4a)

Перейдем в домашний каталог пользователя. Далее, пользуясь утилитой find, найдем все изображений c расширением .png.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/af28711e-03d3-4bff-99c6-71f60b185d5a)

Найдем все директории в домашнем каталоге
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/cba629dd-5241-4072-9d36-eba677ac81f5)

Найдем все файлы, размер которых более 1 Мб

Всего два файла
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a6156b13-3b0b-4635-99d0-a612156324c7)

Найдем все файлы, измененные за последний час (менее 60 мин).

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a154d714-cbe6-44c4-a141-f8c7d86df421)

Найдем все файлы в каталоге MongoDB и скопируем их в каталог PostgreSQL

Синтаксис команды find с действием: -exec command {} \;

command – это команда, которую вы желаете выполнить для результатов поиска. Например:
rm
mv
cp
{} – является результатами поиска.
\; – команда заканчивается точкой с запятой после обратного слеша.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ddfe38f3-30b1-4c5d-a70c-67496ec141af)

Определим полный путь до команд ping и touch

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/fea41bb3-273a-4969-865e-1d45fbad1d99)


##### Изменение атрибутов файлов

Посмотрим установленные атрибуты
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/96e46452-0ba7-4cf2-9529-6870102454a2)

Установим неуязвимость тестовому файлу

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/df474370-9c03-4b16-b680-c1e94de2226d)

##### Архивация и сжатие данных
Создадим архив из каталога AstraLinux, а затем распакуем его. Посмотрим тип файла для архива.
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/3167468e-b8e2-4277-9046-9bee3ddab6e0)

Проделаем сжатие архива astra.tar

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/095005c7-3d89-4dda-a625-44698a7763d6)

Создалим файл размером 100 МБ. Сожмем его с помощью утилиты gzip и добавим в архив astra.tar

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/346c93bc-177c-458a-b1c0-1a21766398c2)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/58cb5fba-44c7-4c2f-ad50-d2f80155abeb)

#### Дополнительно
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/79fab1dd-c257-476b-a756-35e4607dd29e)
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/edfeb7b5-d8cb-4f04-8223-bbb821ff92a2)


Добавим метку безопасности для директории ~/AstraLinux.
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/34617d3d-07c9-4763-a7dd-760e60198177)

Установим утилиту rsync
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/d3963361-d441-4dfc-9ea9-2a832629b519)

Локальное копирование с учетом наличия меток безопасности.
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2fed25fe-147c-4451-b4ec-3c2e25c4b128)






