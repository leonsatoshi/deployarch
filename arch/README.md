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
sudo pacman -S atool bat bc copyq lynx maim moreutils socat firefox unclutter xcape xclip xdotool zip unzip zathura zathura-pdf-mupdf
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

## fcitx5
`sudo pacman -S fcitx5 fcitx5-gtk fcitx5-configtool` \
You must install *fcitx5-gtk*, otherwise GTK based application will not be able to use fcitx5, such as firefox. \
and also export environment variables:
```
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx
```
set to fcitx5 is also ok

## other goodies 
| name(link)                                                    | how to install                                      |
| :---:                                                         | :---                                                |
| [fd](https://github.com/sharkdp/fd)                           | `sudo pacman -S fd`                                 |
| [fzf](https://github.com/junegunn/fzf)                        | `sudo pacman -S fzf`                                |
| [tldr](https://github.com/tldr-pages/tldr)                    | `yay -S tldr-git`                                   |
| [ripgrep](https://github.com/BurntSushi/ripgrep)              | `sudo pacman -S ripgrep`                            |
