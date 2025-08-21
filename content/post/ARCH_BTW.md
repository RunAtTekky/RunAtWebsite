+++
title = 'ARCH BTW'
date = 2025-08-21T14:33:39+05:30
draft = false
tags = ['tech', 'linux']
+++
- Arch BTW
- Hyprland BTW
- Neovim BTW

> Installed [Arch](https://arch.org) and used [Omarchy](https://omarchy.org) to configure my setup on 20th August 2025.

## Disk space
It removes everything on your computer.
Yes. Everything.

It removed my windows and linux mint setups.
Which I wanted to anyway coz windows was only giving me ~60 GB free space for my linux mint.

Now I have ~470 GB free space. SIUUUUUUU

```bash
> df -h
Filesystem        Size  Used Avail Use% Mounted on
dev               2.9G     0  2.9G   0% /dev
run               2.9G  1.4M  2.9G   1% /run
efivarfs          122K   50K   68K  43% /sys/firmware/efi/efivars
/dev/mapper/root  476G  8.3G  467G   2% /
tmpfs             2.9G   15M  2.9G   1% /dev/shm
tmpfs             1.0M     0  1.0M   0% /run/credentials/systemd-journald.service
tmpfs             1.0M     0  1.0M   0% /run/credentials/systemd-resolved.service
tmpfs             1.0M     0  1.0M   0% /run/credentials/systemd-networkd.service
tmpfs             2.9G   12K  2.9G   1% /tmp
/dev/mapper/root  476G  8.3G  467G   2% /home
/dev/mapper/root  476G  8.3G  467G   2% /var/cache/pacman/pkg
/dev/mapper/root  476G  8.3G  467G   2% /var/log
/dev/nvme0n1p1   1022M  255M  768M  25% /boot
tmpfs             580M  140K  580M   1% /run/user/1000
```


## Fastfetch output
![fastfetch](https://i.postimg.cc/0Q5YtwZB/fastfetch.png)

## Issues
OhMyGosh!!!!!
Connecting to college Wi-Fi was a struggle.

My college requires a username and password to connect to it.

[iwd](https://archive.kernel.org/oldwiki/iwd.wiki.kernel.org/) requires a configuration file to connect to such networks.

I was not able to do it. SKILL ISSUE BTW

> I then installed my trusty old [NetworkManager](https://wiki.archlinux.org/title/NetworkManager) and was able to connect to my college Wi-Fi.

