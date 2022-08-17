#### В Vagrantfile из репозитория block_devices добавлены:
* Создание еще 2 дисков /sdf, /sdh и nvme0n5, nvme0n6.
* При запуске виртуальной машины запускается скрипт _raid10.sh_.
* Виртуальная машина запускается с правами root.
___
#### В скрипте _raid10_ реализовано:
* Устанавливаются пакеты mdadm, sgdisk.
* При помощи утилиты __mdadm__ создается программный рейд 10 с именем __raid10__ из блочных устройств __/dev/sde[e-h]__.
* На рейде 10 создается раздел GPT размером 1Гб.
* Информация о созданном рейде 10 записывается в конфигурационный файл __/etc/mdadm/mdadm.conf__.
* При помощи цикла __for__ и утилиты __sgdisk__ на диске __/dev/sdc__ создается 5 партиций по 100Мб.
* Создается точка монтирования __/mnt/raid10/__, форматируется раздел на рейде и монтируется к точке монтирования.
* В __fstab__ записывается информация о монтировании, для последующего автоматического монтирвания рейда. 
___
#### Дополнительно в процессе выполнения домашнего задания командами fail, add был сломан и починен созданный рейд 10.
