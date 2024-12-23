# OTUS.Lesson11
OTUS.Lesson8. Загрузка системы
Задание 1.Включить отображение меню Grub    
nano /etc/default/grub

#GRUB_TIMEOUT_STYLE=hidden
GRUB_TIMEOUT=5

update-grub
root@deb12:# update-grub  
Generating grub configuration file ...  
Found linux image: /boot/vmlinuz-6.1.0-25-amd64  
Found initrd image: /boot/initrd.img-6.1.0-25-amd64  
Found linux image: /boot/vmlinuz-6.1.0-18-amd64  
Found initrd image: /boot/initrd.img-6.1.0-18-amd64  
Found linux image: /boot/vmlinuz-6.1.0-10-amd64  
Found initrd image: /boot/initrd.img-6.1.0-10-amd64  
Warning: os-prober will not be executed to detect other bootable partitions.  
Systems on them will not be added to the GRUB boot configuration.  
Check GRUB_DISABLE_OS_PROBER documentation entry.  
done  
root@deb12:~# reboot  
После перезагрузки мы увидим окно с параметрами загрузки  
![Скриншот 23-12-2024 122657](https://github.com/user-attachments/assets/9606e640-4409-4047-b3d6-97f1bbff8eb7)  

Задание 2. Попасть в систему без пароля несколькими способами  
2.1) init=/bin/bash  
Нажимаем 'e' при выборе выриантов загруки и добавляем init=/bin/bash в параметры загрузки  
![Скриншот 23-12-2024 112922](https://github.com/user-attachments/assets/b7b75ef1-ade0-4adc-b09c-9994b31cac21)  
Видим, что файловая система на ходится в состоянии ro, перемонтируем ее в rw  
![Скриншот 23-12-2024 113052](https://github.com/user-attachments/assets/22ecb668-ae06-409d-99bb-6341a3a64d92)  

2.2) Recovery mode  
При выборе вариантов загруки выбираем advanced options  
![Скриншот 23-12-2024 113143](https://github.com/user-attachments/assets/a7e53811-170e-4d15-b1e5-b1fa81dfe470)  
система загрузится и будет предложено ввести root-пароль  
![Скриншот 23-12-2024 113210](https://github.com/user-attachments/assets/2d4e18fa-a97d-41f4-9c4d-07164e18b0f8)  

3) Установить систему с LVM, после чего переименовать VG
Выводим текущее состояние командой vgs, далее меняет имя нашей volume группы и меняем в grub.cfg старое имя VG на новое, далее перезагружаемся
![Скриншот 23-12-2024 121738](https://github.com/user-attachments/assets/35534dda-a486-465e-9bd2-780463b2a8c8)  
После перезагрузки мы видим что система что то чистит во время первой загрузки после изменения имени VG
![Скриншот 23-12-2024 121925](https://github.com/user-attachments/assets/3b4255c9-955c-4fa7-b39a-3cb5ff79858e)

Загрузились и проверяем VG  
![Скриншот 23-12-2024 122246](https://github.com/user-attachments/assets/be684131-c17c-4f8a-a739-bf3acae93f8b)


 





