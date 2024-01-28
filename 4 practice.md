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





