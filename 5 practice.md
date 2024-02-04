### Работа с текстовой информацией в ОС Astra Linux

Обозначения stdin, stdout, stderr представляют собой макросы, которые используются при написании программ на языке Си (и не только). См. man stdin. Также в каталоге /dev создаются символические ссылки с именами stdin, stdout, stderr, которые указывают на соответствующие файловые дескрипторы стандартных потоков текущего процесса. 
Просмотрим эти ссылки с помощью команды: sudo ls -l /dev/std*

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/c109bf57-68dd-4c3b-8438-a59330e181ab)

Выполнение задания
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/04ccb3a3-4d56-4b60-9edf-83dc42533a9a)

Задание: введите команду echo и запишите для нее любой аргумент.
При выполнении echo без каких-либо аргументов, возвращается пустая строка.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/4662cc57-c07f-4f75-99e1-8aa9a84e2406)

Задание: создайте (или используйте готовые) три файла и объедините их: file1, file2 и file3 в один файл bigfile
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/eafcb205-7c03-4161-85a5-3b778d6bcea8)

Задание: введем команду ls с каталогом % в качестве аргумента:
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/8142704d-89e4-486b-b2a9-a573ffa44ab8)

Задание: перенаправьте поток ошибок в устройство /dev/null.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e1c07ae5-66e0-4f46-8e30-51243bddfdcc)

Задание: с помощью команды cat перезапишите содержимое файла file1, который создается в результате цикла (сделайте ввод нескольких строк). Далее завершите ввод и дополните содержимое файла file1. Просмотрите итоговое содержимое файла.
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/88de0c9d-f68a-4dee-a9e5-fac004b48651)

Задание: введите команду для просмотра содержимого директории, используя постраничный вывод.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/e8217083-b0e7-4256-bfd7-d5fbd187811f)
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ad3c7296-8eb8-49e4-a5ae-ce2d13f18e6c)

### Работа с текстом в редакторе vim

Запустим текстовый редактор vim и введем новое имя файла vim_file
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/108954d0-e3e8-48d2-9ebf-62da3e5252dc)


Задание: удалите и замените часть текста с помощью командного режима, используя различные клавиши для быстрого удаления и замены.
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b7998243-5438-46e3-a18e-4c8dd2cdf466)

Задание: скопируйте несколько начальных символов или строк и вставьте их в конец файла
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2c3c39e7-2ff8-4da9-aff3-38b1f3d06e16)

Сохраните содержимое файла и осуществите выход из редактора
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ac4b9fb8-170c-4297-adac-9bde85a865b9)


Снова откройте файл в редакторе и осуществите поиск и замену любого символа.
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9e847466-5b35-4929-993c-19b10365a770)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/4b67deab-e90e-4393-8cef-0390777a3a43)
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/6ba5dd23-bf7c-44ab-b6ed-861ede5cf7ab)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7270a826-936f-43d6-a126-6c3be52c3952)

Дополнительно
Команда wc
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/aaf752fc-2b32-4129-8198-6477989222e4)

Показ файла, отсортированных c помощью sort:
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/15022995-c0bd-4f81-8081-a22c9c42ee92)

Добавим команду cut к предыдушему примеру
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2b79033f-c408-43e8-a088-068174949be2)

Работа команды uniq
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/b41b445c-ec2f-43b1-b529-2e0fa65de695)

Исползования команды tr
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/daf4e132-b283-4def-8406-293b25594302)

Результат работы команды tee
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/7de667a9-855f-4204-b9c8-66200a573bbc)

Изучим текстовые редакторы grep, sed, awk при конвейерной обработке текстовых потоков и проделайте примеры ниже.

– grep – поиск с использованием базового набора метасимволов регулярных выражений;
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/2739d760-95ef-4f1e-b154-058fa83b020f)

– egrep (grep -E) – поиск с использованием расширенного набора метасимволов регулярных выражений;
– fgrep (grep -F) – поиск по «фиксированной» строке (специальные значения метасимволов игнорируется).

Утилита sed используется для редактирования текстовых потоков.
Формат утилиты sed:
1) выводятся первые десять строк, полученных от ps: PasswordAuthentication no
ps -el | sed -n '1,10 p'
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/3a1d368d-f601-4cca-9ec6-ffe8b04515ce)
Команда для настройки ssh
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/fb7f3e0b-c7bd-4492-ad64-1d4ddf41788f)

Команда awk
![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/44c558e0-3bc7-40f1-ad46-af25c6983cf5)










