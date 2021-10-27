# Arch Linux Installation
- Make Bootable USB or try it on Virtualbox
- If want EFI boot then enable it in BIOS or VBox settings
- If change Default(English) key map then find key map and load it
  ```bash
  ls /usr/share/kbd/keymaps/**/*.map.gz | less
  loadkeys de-latin1
  ```
- `ping google.com`
- set time pool
  ```bash
  timedatectl set-ntp true
  timedatectl status
  ```
- Partition the Drive
  ```bash
  fdisk -l
  fdisk /dev/sda
  # create partition table
  > g # GPT
  > n # new partition for EFI
  > 1
  > +550M # last sector
  > n # for swap
  > 2
  > +2G #  last sector
  > n
  > 3
  > t # change the partition type
  > 1
  > 1 # type 1 EFI system
  > t
  > 2
  > 19 # type 19 linux swap
  > w # write the partitions
  ```
- Make file system
  ```bash
  mkfs.fat -F32 /dev/sda1
  mkswap /dev/sda2
  swapon /dev/sda2
  mkfs.ext4 /dev/sda3
  ```
- Mount install target drive
  ```bash
  mount /dev/sda3 /mnt
  ```
- Base system install
  ```bash
  pacstrap /mnt base linux linux-firmware
  ```
- Generate fstab
  ```bash
  genfstab -U /mnt >> /mnt/etc/fstab
  ```
- change root
  ```bash
  arch-chroot /mnt
  ```
- set timezone
  ```bash
  ls /usr/share/zoneinfo/
  ln -sf /usr/share/zoneinfo/Asia/Dhaka /etc/localtime
  ```
- Hardware clock
  ```bash
  hwclock --systohc
  ```
- Change locale
  ```bash
  pacman -S nano
  nano /etc/locale.gen
  # uncomment en_US.UTF-8 UTF-8
  locale-gen
  ```
- set hostname
  ```bash
  nano /etc/hostname
  # write archbox or any hostname you like
  ```
- write hosts file
  ```bash
  nano /etc/hosts
  127.0.0.1	localhost
  ::1		localhost
  127.0.1.1	archbox.localdomain	archbox
  ```
- change root password and create new user
  ```bash
  passwd root
  useradd -m shadhin
  passwd shadhin
  usermod -aG wheel,audio,video,storage shadhin
  pacman -S sudo
  EDITOR=nano visudo
  # uncomment %wheel ALL=(ALL) ALL line
  ```
- Install GRUB
  ```bash
  pacman -S grub
  pacman -S efibootmgr dosfstools os-prober mtools
  mkdir /boot/EFI
  mount /dev/sda1 /boot/EFI
  grub-install --target=x86_64-efi --bootloader-id=grub_uefi --recheck
  grub-mkconfig -o /boot/grub/grub.cfg
  ```
- Install some packages
  ```bash
  pacman -S networkmanager git vim curl wget
  systemctl enable NetworkManager
  exit
  umount -l /mnt
  reboot or shutdown
  ```
- Install driver
  ```bash
  # for virtualbox
  sudo pacman -S xf86-video-fbdev
  # intel check wiki
  
  # amd
  
  # nvidia
  
  sudo pacman -S xorg xorg-xinit nitrogen picom firefox base-devel
  ```
- AUR setup
  ```bash
  git clone https://aur.archlinux.org/yay-git.git
  ls -la
  cd yay-git
  makepkg -si
  ```
- setup window manager etc
  ```bash
  yay -S nerd-fonts-mononoki
  # add distrotube repo
  sudo nano /etc/pacman.conf
    [dt-arch-repo]
	SigLevel = Optional DatabaseOptional
	Server = https://gitlab.com/dwt1/$repo/-/raw/master/$arch
  
  sudo pacman -Syyu
  sudo pacman -S dwm-distrotube-git st-distrotube-git dmenu-distrotube-git
  cp /etc/X11/xinit/xinitrc /home/shadhin/.xinitrc
  reboot
  startx
  ```
