# input methods (ibus)
 
## Chinese
- 安装 
```
pacman -S ibus-rime # arch
emerge -av ibus-rime # gentoo

# other distro:
# https://github.com/rime/home/wiki/RimeWithIBus
``` 
- 追加到 `.zshrc` or `.zprofile`:
```
ibus-daemon -drx
export GTK_IM_MODULE=ibus
export QT_IM_MODULE=ibus
export XMODIFIERS=@im=ibus

```
- 下载输入方案, 部分发行版可能不提供，所以使用[plum](https://github.com/rime/plum)进行手动安装:
```
curl -fsSL https://git.io/rime-install | bash 
cd plum
./rime-install double-pinyin
./rime-install emoji
```
- 小鹤双拼
追加以下内容到`~/.config/ibus/rime/default.yaml`
```
schema_list:
  - schema: double_pinyin_flypy
```
- 默认键位
Ctrl + \` 打开输入方案选择，逗号句号候选词翻页, 可在 `~/.config/ibus/rime/key_bindings.yaml` 定制


## Japanese 
- install mozc
