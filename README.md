# personal-multiboot
Me working with my laptop and trying to multiboot it without having to completely reinstall everything. Successfully tested for Arch, Ubuntu, and Windows.

## Initial state:-
Output of `fdisk -l /dev/nvme0n1`
```
Device              Start        End   Sectors   Size Type
/dev/nvme0n1p1       2048     534527    532480   260M EFI System
/dev/nvme0n1p2     534528     567295     32768    16M Microsoft reserved
/dev/nvme0n1p3     567296  671655935 671088640   320G Microsoft basic data
/dev/nvme0n1p4 1998360576 2000408575   2048000  1000M Windows recovery environme
/dev/nvme0n1p5 1855623168 1998360575 142737408  68.1G Linux filesystem
/dev/nvme0n1p6  824295424 1793742847 969447424 462.3G Linux filesystem
```
I have grub installed with a theme that I'll link to later if I remember to. 

## Result:-
Will add an image here later. But I used the refind-black theme, and it looks dope asf.

## Process:-
Following [this](https://medium.com/@manujarvinen/setting-up-a-multi-boot-of-5-linux-distributions-ca1fcf8d502) guide, I first installed refind by installing the deb and running `sudo dpkg -i <filename-whatever>`. 
(I don't remember if I ran the refind-install script or not (rip the purpose of this repo lol).

Anyways, then I cloned the theme refind-theme-regular into the `/boot/efi/EFI/refind` directory using `git clone <repo-url> /boot/efi/EFI/refind/refind-theme-regular`, and edited the refind.conf file to add the line `include refind-theme-regular/theme.conf`   

And voila, on reboot it should work. 

However, it had a lot of options, while I only want windows and ubuntu. 

## Status
![99%](https://progress-bar.dev/99)
