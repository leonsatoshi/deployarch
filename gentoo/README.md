# deploygentoo
you can use any linux distro to install gentoo, do NOT use a live CD cuz' it got no browser to read gentoo wiki.

## .config
this is my gentoo-6.7.5 kernel config file, with dockcer support enabled. \
more spec: \
bluetooth, amd gpu, amd cpu, docker, cloudflare-warp


## .config-6.5.6-intel-nvidia-docker
this is my gentoo-6.5.6 kernel config file, with dockcer support enabled. \
more spec: \
intel CPU & wireless card, GPT partition table(using uuid in fstab)

## before chroot
1. `mount /dev/somepart /gentoo`
2. `cd /gentoo && wget some-stage3.tar.xz`
3. `tar xpvf stage3-*.tar.xz --xattrs-include='*.*' --numeric-owner`
4. `cp --dereference /etc/resolv.conf /gentoo/etc/`
5. put portage conf into /gentoo, edit in host machine by nvim if needed because default stage3 provides nano which...
6. `ch_gentoo.sh`: this script does mount and chroot things

## in chroot
0. tweak make.conf
1. `emerge-webrsync && emerge --sync`
2. eselect profile list
   eselect profile set [n]
3. `emerge --ask --verbose --update --deep --newuse @world`, `-avDuN` for short
4. change USE in make.conf
5. set locale and timezone
6. install firmware and source
7. kernel config, enble GPT if you use uuid in /etc/fstab, enable EFI stub for showing kernel message when booting
8. make kernel, install a bootloader(I use [*refind](https://github.com/0n3W4y7ick3t/deployLinux/tree/main/refind))

## config
1. wifi: install iwd and dhcpcd, enable the services by `rc-service add [service] boot/default`if you use wifi, iw can be configured by add a file with SSID.psk as its name, filled with contents below(if you only use cable network, iwd is not needed.):
```
# /var/lib/iwd/SSID.psk
[Security]
Passphrase=you super secret password
```

2. install dwm and other goodies.

## other goodies
| name(link) | how to install |
| :---: | :--- |
| [fd](https://github.com/sharkdp/fd) | `emerge -av sys-apps/fd` |
| [fzf](https://github.com/junegunn/fzf) | `emerge -av app-shells/fzf` |
| [tldr(c-clinet)](https://github.com/tldr-pages/tldr-c-client) | `emerge -av libzip libcurl && make && make install` |
| [ripgrep](https://github.com/BurntSushi/ripgrep) | `emerge sys-apps/ripgrep` |
