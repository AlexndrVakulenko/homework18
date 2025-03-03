# Домашнее задание " Резервное копирование "


vagrantfie создает 2 VM ubuntu-22.04 backup и client.
На VM backup добавлен дополнительный диск 2Gb - файл /backup/sata1.vdi в текущей директории.

Workbook ansible backup_workbook.yml:

 на VM backup настраивает дополнительный диск, добавляет пользователя borg, устанавливает пакет borgbackup.

 на VM client устанавливает пакет borgbackup, копирует borg-backup.service и borg-backup.timer из текущей директории запуска, генерит ключи ssh.


 Провека работы borgbackup:





![Image alt](https://github.com/AlexndrVakulenko/homework17/blob/main/01_%D0%9F%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0_service_nginx.png)

