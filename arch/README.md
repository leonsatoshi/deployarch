# deployarch

## bootloader
see [*refind*](https://github.com/0n3W4y7ick3t/deployLinux/tree/main/refind) folder

### genarate a wifi profile:
`wpa_passphrase SSID password >> /etc/wpa_supplicant/wpa_supplicant.conf` \
use `sv start wpa_supplicant` to connect wifi and continue

## setup pacman
```
Color
ILoveCandy
ParallelDownloads = 8
```

## sign keyring(if you didnt run into any relative error, skip this)
1. make changes in /etc/pacman.conf: `SigLevel  = TrustAll`
2. `pacman -Syy archlinux-keyring`, after step 2, this should not return any signature error.
3. change SigLevel back to original, i.e. SigLevel = Required DatabaseOptional


## media
```
sudo pacman -S mpc mpd mpv ncmpcpp pipewire-pulse pulsemixer pamixer ueberzug lf mediainfo poppler ffmpegthumbnailer sxiv feh
```
## system
```
sudo pacman -S btrfs-progs ntfs-3g dunst dhcpcd gnome-keyring libnotify man-db  polkit wpa_supplicant
```

## X
```
sudo pacman -S arandr python-qdarkstyle ttf-hack ttf-fira-code noto-fonts-emoji xorg-server xorg-xwininfo xorg-xprop xorg-xdpyinfo xorg-xbacklight xorg-xinput
```

## utility
```
sudo pacman -S atool bat bc clipmenu lynx maim moreutils socat firefox unclutter xcape xclip xdotool zip unzip zathura zathura-pdf-mupdf
```
## AUR
install yay:
```
pacman -S --needed git base-devel
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```
`yay -S htop-vim picom-git`
