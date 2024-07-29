# hardkerneled

## TO DO: 
* Glances Autostart:
    * Fix problem using `glances.services` in `cd /etc/systemd/system/` via `sudo systemctl enable glances.service`

<img src="https://wiki.odroid.com/_media/odroid-xu4/hardware/xu4_detail.jpg">

## Hardware
Hardkernel Odroid-[XU4Q](https://www.hardkernel.com/product-tag/odroid-xu4q/) (copper heat sink) and Hardkernel Odroid-[XU4](https://www.hardkernel.com/product-tag/odroid-xu4/) (fan): 
* CPU: Samsung Exynos 5 Octa (5422) with big.LITTLE-Architecture and Heterogeneous Multi-Processing as used in Galaxy S5 smartphone (2014; 28nm)
  * 4x Cortex-A15 Quad 2.0GHz 
  * 4x Cortex-A7  Quad 1.4GHz
* GPU: Mali-T628 MP6 
  * OpenGL ES 3.1 / 3.0 / 2.0 / 1.1
  * OpenCL 1.2 Full profile
* RAM: 2GB LPDDR3 w/ 750Mhz, 12GB/s memory bandwidth, 2x32bit bus
* HDMI: 1.4a with via Type-A
* USB
  * USB 3.0: 2 ports via USB A
  * USB 2.0: 1 port via USB A
* Storage: possible via eMMC or MicroSD Card
* Ethernet:	10/100/1000Mbps Ethernet with RJ-45 Jack
* Power Supply: 5V/4A
* Storage: 64 GB SanDisk SD-Card
* Wifi-Dongle: Ralink RT5370 chipset
* Case: [Black](https://www.hardkernel.com/shop/odroid-xu4-case-black/)

Take-Away: Hardkernel's done a great job in general, unfortunately though USB-connections are very buggy, basically only one of the three USB interfaces works reliably. Especially after years in use. Also, built-in Wifi is definitely going to be a must-have for future SBCs. 

### Hardkernel Linklist: 
* [Odroid XU-4 Specs](https://wiki.odroid.com/odroid-xu4/hardware/hardware)
* [Odroid-XU4 Manual](https://magazine.odroid.com/odroid-xu4)
* [Odroid-XU4 User Forum](https://forum.odroid.com/viewforum.php?f=92&sid=c825d92a8c321982a51e468a8b7cc603)
  * [Ubuntu](https://forum.odroid.com/viewforum.php?f=95)
  * [Android](https://forum.odroid.com/viewforum.php?f=94)
* [Odroid XU-4 Wiki](https://wiki.odroid.com/odroid-xu4/odroid-xu4)
* [Hardkernel FTP](https://dn.odroid.com/)

<img src="https://dn.odroid.com/homebackup/201506191222574523.png">

## Operating System
[Android](https://wiki.odroid.com/odroid-xu4/os_images/android/android): 
* [Odroid Download FTP-Server](https://dn.odroid.com/5422/ODROID-XU4/Android/4.4.4_Alpha_7.1_Feb-22-2021/)
* [voodik's Lineage OS alpha images for XU*](https://oph.mdrjr.net/voodik/5422/ODROID-XU3/Android/)
  * [Lineage 16.0 w/ Android 9.0 alpha](https://oph.mdrjr.net/voodik/5422/ODROID-XU3/Android/lineage-16.0/Alpha-0.4_13.09.21/)
  * [Forum Post](https://forum.odroid.com/viewtopic.php?f=94&t=42267)

[Ubuntu](https://wiki.odroid.com/odroid-xu4/os_images/linux/start):
* [Odroid Download FTP-Server Germany/EU](https://de.eu.odroid.in/ubuntu_20.04lts/XU3_XU4_MC1_HC1_HC2/) with all available images
* MATE: 
  * [Ubuntu MATE 20.04.3 LTS w/ Kernel v5.4.142](https://wiki.odroid.com/odroid-xu4/os_images/linux/ubuntu_5.4/mate/20210926)
  * default user/passwd: odroid/odroid, root/odroid
* Minimal
  * [Ubuntu Minimal 20.04.3 LTS w/ Kernel v5.4.149](https://wiki.odroid.com/odroid-xu4/os_images/linux/ubuntu_5.4/minimal/20210928)
  * default user/passwd: root/odroid

### Recommended Flasher: 
* [Etcher](https://www.balena.io/etcher/)

## Software

### First Things First
Get latest updates for Ubuntu & installed software zoo:
```
sudo apt-get update && sudo apt-get -y upgrade
```
[Enable SSH](https://linuxize.com/post/how-to-enable-ssh-on-ubuntu-20-04/) to connect headlessly from network: 
```
sudo apt install openssh-server
sudo systemctl status ssh
sudo ufw allow ssh
```
SSH connection from within network now possible via 
```
ssh username@ip_address
```
where default:
* username: 'odroid'
* ip_address: 'odroid' otherwise search with `ip a` in odroid terminal for the exact ip-address
* passwd: 'odroid'

Close the connection via `exit`.

Hint: Configure local router to always assign the identical ip address to odroid.

### Emby Media Server
* Webseite: [emby.com](https://emby.media/)
* GitHub repository: [Emby Media Browser](https://github.com/MediaBrowser/Emby)
* Download for Ubuntu: 
  * [choose armv7](https://emby.media/linux-server.html) 
```
dpkg -i emby-server-deb_4.6.7.0_armhf.deb
```
  * open [http://localhost:8096](http://localhost:8096) or [localhost:8096/InstallationWizard](http://localhost:8096/web/wizardstart.html) in your browser
* Installation Guide: [official](https://support.emby.media/support/solutions/articles/44001159243-installation)
```
systemctl enable emby-server.service
```

Verify via: 
```
systemctl status emby-server -l
```

### Calibre Web
* Calibre: [Homepage](https://calibre-ebook.com/)
* CalibreWeb: [GitHub Repository)[https://github.com/janeczku/calibre-web]

Requirements: 
* Calibre installed, executed in order to created a db for CalibreWeb to read
```
sudo apt-get install calibre 
calibre
```
* Installation via Python ([Mint Guide](https://github.com/janeczku/calibre-web/wiki/How-To:Install-Calibre-Web-in-Linux-Mint-19-or-20)):
  1. make sure to have python3 > 3.5
```
python --version
python3 --version
```
  2. make sure to have pip acivated for python3 (sic!)
```
sudo apt install python3-pip
pip3 --version
sudo -H pip3 install --upgrade pip
sudo apt install python3-dev
sudo apt-get install python3-setuptools
python3 -m pip install wheel

```
  3. Open folder `cd /opt/calibre-web/`in terminal:
```
python3 -m pip install venv
python3 -m venv venv
./venv/bin/python3 -m pip install calibreweb
./venv/bin/python3 -m calibreweb
```
  4. install `calibreweb`
```
pip install calibreweb
```
  5. Open [http://localhost:8083](http://localhost:8083) in your browser, if necessary with defaults:
      * user: 'admin'
      * passwd: 'admin123'  

#### How to run CalibreWeb on boot?
* [Instructions](https://github.com/janeczku/calibre-web/wiki/Setup-Service-on-Linux#start-calibre-web-as-service-under-linux-with-systemd)
in `cd /etc/systemd/system/` create a file via `touch cps.service` with contents `sudo nano cps.service`:
```
[Unit]
Description=Calibre-Web

[Service]
Type=simple
User=odroid
ExecStart=/opt/venv/bin/python /opt/venv/bin/cps

[Install]
WantedBy=multi-user.target
```
Then activate service in systemctl:

```
sudo systemctl enable cps.service
```
and validate success:
```
systemctl | grep cps
systemctl status cps -l

```

#### How to automatically add new elements into Calibre on boot
in `cd /etc/systemd/system/` create a file via `touch update-db.service` with contents `sudo nano update-db.service`:
```
[Unit]
Description=Update Calibre DB with every startup of machine

[Service]
Type=simple
ExecStart=/bin/bash /media/Datas/Calibre/update-db.sh

[Install]
WantedBy=multi-user.target
```
Then activate service in systemctl:
```
sudo systemctl enable update-db.service
```
and validate success:
```
systemctl status update-db -l
```

### How to bind NTFS HDD
1. Install package `ntfs-3g`
```
sudo apt-get install -y ntfs-3g
```
2. Get location of plugged HDD
```
sudo blkid
/dev/mmcblk1p2: LABEL="rootfs" UUID="2134-432432-23423-234234-123112" TYPE="ext4" PARTUUID="1234312-12"
/dev/mmcblk1p1: SEC_TYPE="msdos" LABEL_FATBOOT="boot" LABEL="boot" UUID="1234-1234" TYPE="vfat" PARTUUID="1234312-12"
/dev/loop0: TYPE="squashfs"
/dev/loop1: TYPE="squashfs"
/dev/sda1: PARTLABEL="Microsoft reserved partition" PARTUUID="123123-234234-234234-234234-234234"
/dev/sda2: LABEL="MediaStash" UUID="2342343242" TYPE="ntfs" PTTYPE="atari" PARTLABEL="Basic data partition" PARTUUID="656rtzrtz-rtzrtz-rtzrtz-rtztz-rtzrtz"
```
-> sda2 with UUI="2342343242"
3. Create folder via `sudo mkdir /media/Datas` and mount the partition into `/media/Datas`but first do `sudo umount /dev/sda2`
```
sudo mount /dev/sda2 -t ntfs-3g -o permissions /media/Datas/
```
4. In `cd /etc/` edit file fstab via `sudo nano fstab`
```
/dev/sda2 /media/Datas ntfs-3g defaults 0 0
```
### How to perform sanity checks on your HDD?
TO DO

Finally, consider using Windows' native tool `chkdsk` to do this the proper and safer way.

### How to perform a full image backup
TO DO

### Which devices are currently mounted via USB?
Use either: 
* [fixed disk](https://wiki.ubuntuusers.de/fdisk/): `sudo fdisk -l`
* [disk free](https://wiki.ubuntuusers.de/df/): `df -Th | grep media`
* [list block devices](https://wiki.ubuntuusers.de/lsblk/): `lsblk` or try `lsblk | grep sd`
* [block id](https://wiki.ubuntuusers.de/blkid/): `sudo blkid`
* [list usb devices](https://wiki.ubuntuusers.de/lsusb/): `lsusb` identical to `usb-devices`
* [display message](https://wiki.ubuntuusers.de/dmesg/): `sudo dmesg | grep usb`

### How to turn off various power saving modes
* Wifi: 
If `iwconfig` prints "Power Management:on", try
```
sudo nano /etc/NetworkManager/conf.d/default-wifi-powersave-on.conf
```
Default value under "[connection]" is "wifi.powersave = 3". Change this value to "2". See [this](https://gist.github.com/jcberthon/ea8cfe278998968ba7c5a95344bc8b55), [this](https://unix.stackexchange.com/a/315400) or [this](https://askubuntu.com/a/860754). Then restart NetworkManager by 
```
sudo systemctl restart NetworkManager
```
* USB:
```
sed -i 's/GRUB_CMDLINE_LINUX_DEFAULT="/&usbcore.autosuspend=-1 /' /etc/default/grub
update-grub
systemctl reboot
```
* General:
```
sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target
```

Verify after reboot by typing into terminal `cat /sys/module/usbcore/parameters/autosuspend`. Expected value is "-1"

### How to savely reboot or shutoff via ssh
```
sudo poweroff
sudo reboot
```
### Whats the very best task and resource manager for cli?
`glances`, `htop`, for trend lines use `dstat`
```
python3 -m pip install glances
sudo apt-get install python3-bottle
sudo apt-get install -y htop
sudo apt-get install -y dstat
```
Monitor from network: 
```
glances -w
```
Navigate to [http://0.0.0.0:61208/](http://0.0.0.0:61208/) on your browser.

Start glances on boot (see official [Glances Wiki entry](https://github.com/nicolargo/glances/wiki/Start-Glances-through-Systemd)):
```
cd /etc/systemd/system/
touch glances.service
sudo nano glances.service
```
Fill file with contents: 
```
[Unit]
Description=Glances
After=network.target

[Service]
ExecStart=/usr/local/bin/glances -w
Restart=on-abort
RemainAfterExit=yes

[Install]
WantedBy=multi-user.target
```

Enable via `systemctl`: 
```
sudo systemctl enable glances.service
```

### Where am I?
`pwd`

# Skripting
* tempmon.sh: shows cpu temperature by core; updated every 3 seconds - lies in `/home/odroid`
```
#!/bin/bash
watch -n 3 cat /sys/devices/virtual/thermal/thermal_zone*/temp
```
allow execution: 
```
chmod +x tempmon.sh
```
and perform execution: 
```
cd ./home/odroid/
./tempmon/
```
