# OTUS.Lesson11
OTUS.Lesson8. Загрузка системы
Задание 1.Включить отображение меню Grub    
nano /etc/default/grub  
  
#GRUB_TIMEOUT_STYLE=hidden  
GRUB_TIMEOUT=5  
  
update-grub  
root@deb12:~# update-grub  
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


