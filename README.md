1. В vagrantfile из репозитория block_devices добавлены еще по 2 по диска /sdf, /sdh и nvme0n5, nvme0n6.
2. Собран программный рейд 10 из дисков /sde, /sdf, /sdg, /sdh.
3. Диск /sde выведен из строя командой --fail. В рейд добавлен диск /sdc, рейд продолжает функционировать.
4. Собранный рейд прописан в конфигурационный файл /dev/mdadm.conf, файл выложен в репозиторий в git.
5. Программой parted на диске /sdc создан раздел gpt и создано 5 партиций. Партиции отформатированы, проверено, что диски монтируются в /mnt.
