# Ejemplos uso mount y umount en Linux
## Bash, Filesystem 
### URL: https://www.jesusninoc.com/2017/04/17/ejemplos-uso-mount-y-umount-en-linux/
```Shell
#Ver todos los dispositivos montados
mount

#Montar todos los sistemas de archivos que se encuentran en el fichero fstab
mount -a

#Montar un dispositivo indicando el sistema de archivos o tipo de dispositivo
mount -t ext3 /dev/sda1 /mnt/disco1
mount -t ext4 /dev/sda2 /mnt/disco2

#Desmontar un punto de montaje
umount /disco1

#Desmontar varios puntos de montaje
umount /disco1 /disco2

```
