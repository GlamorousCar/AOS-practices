### Управление файловыми системами

Добавим 2 диска к вируталке 

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/9d0754af-a25a-43da-9296-7e73f64e5b7b)

Разметим первый диск с помощью утилиты fdisk

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/cf8a9d0b-11c6-4e59-ae83-506e20dd5af8)

Проверим созданные разделы первого диска

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/c625f2cc-1a5f-4bb0-a507-afea8286435c)

Разметим второй диск с помощью утилиты parted, разбейте его на 2 примерно одинаковых раздела.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/69e2a808-4592-492b-aa1a-25c047a4df9e)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/0c92961c-a52a-4584-925c-c92aacf4ba8b)

### Создание файловых систем

Создадим файловые системы на первых разделах – ext4, на вторых – ext2.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/845d7dee-a1c0-41e3-b739-94ead5384c94)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/d456a969-6205-42b6-a587-97274f6965a2)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/672d8b34-7b4a-4ad2-8786-3de5e045d084)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ff53b567-48b2-4109-9220-defc52a18f5b)


Создадим точки монтирования /opt/data/storage, /opt/data/cache, /opt/data/export, /opt/data/log для ранее созданных разделов.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/ec81b015-7563-4423-b4f3-9660a8e5b4ca)

Монтирование файловых систем

Обеспечим автоматическое монтирование файловых систем при загрузке. Для первого диска используем файл /etc/fstab

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/4c097718-3698-4dd6-b631-7656e390b544)

Обеспечим автоматическое монтирование файловых систем при загрузке. Для второго создадим юниты типа mount

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/99a146a6-41a8-4d30-b585-22cd6ae73a77)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/a695f766-2ccf-4d26-9f42-4e41aa8d0db3)

Выполним монтирование ФС и сделаем так, точка монтирования, описанная в юните, автоматически монтировалась при загрузке системы

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/dfef5b72-132c-4076-8ba8-d4e5abc11077)

#### Использование расширенных утилит для просмотра свойств дисков

Посмотрим данные о созданных разделах первого диска. Обратим внимание на то, какая из ФС является журналируемой.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/5b7c9cd4-4491-43e6-b00d-97d28a5041d3)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/17fd6886-30a5-423d-ad04-530c2401253b)

Отобразим содержимое суперблока для разделов второго диска.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/c7baf021-61d9-4abd-b118-0da039a78552)

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/3d963f02-d3b3-4c67-bc6a-8121992dd7a7)

Посмотрите информацию о свободном месте в областях данных и inode для первого и второго диска.

![image](https://github.com/GlamorousCar/AOS-practices/assets/48102376/f7919e80-9f5a-4f00-a029-9110b5637123)








