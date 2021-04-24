# personal-multiboot
Me working with my laptop and trying to multiboot it without having to completely reinstall everything, while also making the boot menu prettier using refind. Successfully tested for Arch, Ubuntu, and Windows.

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
![refind-black-wua](https://user-images.githubusercontent.com/46960231/115958379-e25bba00-a524-11eb-945f-594c19b37c7e.png)
*looks dope asf*

My partitions finally look like this:-
```
Device              Start        End   Sectors  Size Type
/dev/nvme0n1p1       2048     534527    532480  260M EFI System
/dev/nvme0n1p2     534528     567295     32768   16M Microsoft reserved
/dev/nvme0n1p3     567296  671655935 671088640  320G Microsoft basic data
/dev/nvme0n1p4 1998360576 2000408575   2048000 1000M Windows recovery environmen
/dev/nvme0n1p5 1510516736 1657317375 146800640   70G Linux filesystem
/dev/nvme0n1p6  671655936 1510516735 838860800  400G Linux filesystem
/dev/nvme0n1p7 1657317376 1867032575 209715200  100G Linux filesystem
/dev/nvme0n1p8 1867032576 1992861695 125829120   60G Linux filesystem
/dev/nvme0n1p9 1992861696 1998360575   5498880  2.6G Linux swap
```
![gparted-post-archInstall](https://user-images.githubusercontent.com/46960231/115958568-93faeb00-a525-11eb-856d-c368e8a622c5.png)
*Nice, a lot of paritions, I'm learning to not be intimidated by these now :)*
## Process:-
Following [this](https://medium.com/@manujarvinen/setting-up-a-multi-boot-of-5-linux-distributions-ca1fcf8d502) guide, I first installed refind by installing the deb and running `sudo dpkg -i <filename-whatever>`. 
(I don't remember if I ran the refind-install script or not (rip the purpose of this repo lol).

Anyways, then I cloned the theme refind-theme-regular into the `/boot/efi/EFI/refind` directory using `git clone <repo-url> /boot/efi/EFI/refind/refind-theme-regular`, and edited the refind.conf file to add the line `include refind-theme-regular/theme.conf`   

And voila, on reboot it should work. 

However, it had a lot of options, while I only want windows and ubuntu and any other that I might add.

So well, to do that I just rounded up all the .efi files in my /boot/efi directory, and added them in the refind.conf file so that it looks like:-

`dont_scan_files grub64.efi,bootx64.efi,notyou.efi,yadayada.efi`


Also, since I didn't like the "Booting OS dialog that openend after I selected something in refind, I had to add it in the `use_graphics_for` or something line and add linux there along with macOS, also added windows to finally make it:

`use_graphics_for osx, linux, microsoft`

## Status
![99%](https://progress-bar.dev/99)

Gonna keep it at 99% since even though I'm satisfied with this, this worked pretty easily and this might not work for many other distros as well.

