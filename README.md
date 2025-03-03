# Домашнее задание " Резервное копирование "


vagrantfie создает 2 VM ubuntu-22.04 backup и client.
На VM backup добавлен дополнительный диск 2Gb - файл /backup/sata1.vdi в текущей директории.

Workbook ansible backup_workbook.yml:

 на VM backup настраивает дополнительный диск, добавляет пользователя borg, устанавливает пакет borgbackup.

 на VM client устанавливает пакет borgbackup, копирует borg-backup.service и borg-backup.timer из текущей директории запуска, генерит ключи ssh.


 Провека работы borgbackup:

Копирование ключа ssh на сервер backup:
![Image alt](https://github.com/AlexndrVakulenko/homework18/blob/main/01_ssh-copy-id.png)

Инициализиализация репозитория borg на backup сервере с client сервера:
![Image alt](https://github.com/AlexndrVakulenko/homework18/blob/main/02_borg_init.png)

Создание бэкапа:
![Image alt]((https://github.com/AlexndrVakulenko/homework18/blob/main/03_borg_create1.png)
![Image alt]((https://github.com/AlexndrVakulenko/homework18/blob/main/04_borg_create2.png)

Просмотр бэкапа:
![Image alt]((https://github.com/AlexndrVakulenko/homework18/blob/main/05_borg_list1.png)
![Image alt]((https://github.com/AlexndrVakulenko/homework18/blob/main/06_borg_list2.png)

Проверка работы borg prune:
![Image alt]((https://github.com/AlexndrVakulenko/homework18/blob/main/07_borg_prune.png)

Запуск и проверка службы таймера:
![Image alt]((https://github.com/AlexndrVakulenko/homework18/blob/main/08_borg_timer.png)

Результат работы таймера - создание нового бэкапа:
![Image alt]((https://github.com/AlexndrVakulenko/homework18/blob/main/09_borg_timer_result.png)



