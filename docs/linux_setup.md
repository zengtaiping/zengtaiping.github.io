# Linux Setup

## clean your mac os trash by command line
```
sudo du -d 1 -h | sort -h
sudo rm -rf ./folder
```

## install windows font on linux
```
sudo mkdir /usr/share/fonts/WindowsFonts
sudo cp /Windowsdrive/Windows/Fonts/* /usr/share/fonts/WindowsFonts
sudo chmod 755 /usr/share/fonts/WindowsFonts/*
fc-cache #regenerate the font cache figuration
```

## samba local visit
any devices to linux

#### 1. install samba service
- system update
```
sudo apt-get upgrade
sudo apt-get update
sudo apt-get dist-upgrade
```
- install samba
```
sudo apt-get install samba samba-common
```
- set username and password
```
sudo smbpasswd -a username
```
- edit configuration file
```
sudo gedit /etc/samba/smb.conf
```
- add to the end of the last line
```
[sharefoldername]
comment = share folder
browseable = yes
path = /home/share folder path
create mask = 0700
directory mask = 0700
valid users = username
force user = username
force group = username
public = yes
available = yes
writable = yes
```
- set folder access permissions
```
sudo chmod 777 /home/share folder path
```

## ssh access
#### enable ssh on linux
```
sudo apt update
sudo apt install openssh-server
sudo systemctl status ssh
sudo ufw allow ssh
```

#### ssh visit
```
ssh username@ip_address
```
- ip command to find your ip
```
ip a
```