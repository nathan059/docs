## Boot Loader
GRUB - 

### Grub 2
/etc/grub2.cfg is a symbolic link to:
- BIOS - /boot/grub2/grub.cfg
- UEFI - /boot/efi/EFI/centos/grub.cfg

The GRUB 2 configuration file `grub.cfg` is generated by invoking `grub2-mkconfig`

The file is generated according to template files located in /etc/grub.d/, and custom settings in the /etc/default/grub file



#### Breaking the boot sequence
On grub menu press e to edit or c for a command prompt

On edit screen alternative runlevel targets can be set
- `systemd.unit=rescue.target`
- `systemd.unit=emergency.target`
- `init=/sysroot/bin/sh`

Recover root password
- `rd.break`

```bash
mount -o remount,rw /sysroot
chroot /sysroot
passwd
touch /.autorelabel
```



### Grub Legacy