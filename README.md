# personal-multiboot
Me working with my laptop and trying to multiboot it without having to completely reinstall everything.


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

## Goal:-
Something similar to this:-
![image](https://user-images.githubusercontent.com/46960231/115722238-6d5d7880-a39c-11eb-818c-14f87086936d.png)
*Except with Ubuntu Gnome, Arch, Fedora, and Windows. Maybe ditch Fedora, who knows.*

Since I have a 1TB SSD, I plan on having around 320 ish GB to Windows (should be enough for games ig), 600 can be split 400-200 between Ubuntu and Arch or 400-100-100 including Fedora. I'll figure this out.

## Plan:-
I intend on following [this](https://medium.com/@manujarvinen/setting-up-a-multi-boot-of-5-linux-distributions-ca1fcf8d502) guide. I'll be documenting my steps below as I go on with this.

Also lol, this might be impossible-ish too, so I might give up in between.

## Progress
![0%](https://progress-bar.dev/0)

