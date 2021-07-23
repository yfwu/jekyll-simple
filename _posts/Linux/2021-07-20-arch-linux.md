---
title: 安裝及設置 Arch Linux
category: Linux
layout: post
---

我算是 Arch Linux 的資深玩家了（從 2012 開始都是用 Arch）。不過自從買了 Apple 後，Arch 就是 Mac 內的一個虛擬機，用來當一些小程式的運作環境（例如：Racket）。最近把大主機更新了一輪內置硬體，順便將系統刷成 Arch Linux，當作機器學習運算作業系統。底下摘錄一下安裝完後做了什麼事情。

## 安裝

用的是 [Archfi](https://github.com/MatMoul/archfi)，用來幫我把一些雜七雜八的例如硬碟格式化、`mkinitcpio` 等一鍵搞定。由於是機器學習主機，因此我沒有安裝任何 Xorg 及桌面環境，保持系統整潔。

## 雙作業系統

我主機偶爾會重新啟動到另一個硬碟的 Windows 玩遊戲，所以需要 `os-prober` 來偵測 Windows 的 EFI。`os-prober` 安裝好後會自動在 grub-mkconfig 的時候偵測、添加 Windows。不過這裏有個坑 - 就是要先安裝 `ntfs-3g` 才能偵測。另外還需要將 `/etc/default/grub` 中的 `GRUB_DISABLE_OS_PROBER` 改成 false。

```bash
sudo pacman -S ntfs-3g
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

## yay

以前我都用 `yaourt`，不過這工具已經停止維護很久了，現在要安裝來自 Arch Users Repository，可以使用 [yay](https://github.com/Jguer/yay) 這套以 Go 寫成的工具。

## RAID

我電腦內有四顆硬碟，是組成硬碟陣列使用。使用 `mdadm` 來管理他們。

```bash
sudo fdisk /dev/sdb
```

分割磁區，依次按鈕 `n`（新增）、`t`（選擇類別 29：Liunux RAID）、 `w`（寫入）。

```bash
sudo mdadm -C /dev/md0 -l5 -n4 /dev/sd{b,c,e,g}1 --assume-clean
sudo mount /dev/md0 /database
sudo mkfs.ext4 /dev/md0
```

最後把 md0 的資訊寫入 `/etc/fstab`。可以用 `sudo mount -fav` 來測試掛載有沒有問題。注意一開始生成 `fstab` 的時候選標籤而不是 UUID，不然只是困擾自己 XD

## Wake on LAN

確定網卡是否支援 wake on LAN

```bash
sudo ethtool enp4s0 | grep Wake-on
```

只要 `Wake-on` 是 g 即可。接著在平常的作業系統（如我是 macOS）安裝能發送 magic packet 的軟體即可。
