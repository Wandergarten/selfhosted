# Vault

## TODO: 
* 
## Ideas:

## Documentation: 
### Setup
#### RustDesk
* Homepage: [rustdesk.com](https://rustdesk.com/)
* Documentation: [rustdesk.com/docs](https://rustdesk.com/docs/en/)
* Git: 
    * [Client](https://github.com/rustdesk/rustdesk)
    * [Server](https://github.com/rustdesk/rustdesk-server)
* Installation on Debian: 
    1. Server: 
        1. [Documentation > Self-host > RustDesk Server OSS > Installation via isntall script](https://rustdesk.com/docs/en/self-host/rustdesk-server-oss/install/#install-your-own-server-as-systemd-service-using-a-simple-to-run-install-script) refers to this repository's install script: [github.com/techahold/rustdeskinstall](https://github.com/techahold/rustdeskinstall):
        ```
        ufw allow proto tcp from 192.168.178.70 to any port 22
        ```
    1. Client: 
        1. [Documentation > Linux > Debian](https://rustdesk.com/docs/en/client/#debian-derivatives) via [client repo's releases](https://github.com/rustdesk/rustdesk/releases/latest)
            ```
            wget https://github.com/rustdesk/rustdesk/releases/download/latest/rustdesk-1.3.5-x86_64.deb
            ```
        1. Install .deb file
            ```
            sudo dpkg -i rustdesk-1.3.5-x86_64.deb
            ```


### Regular Admin Cycle
0. Use SSH
```
 ssh chris@192.168.abc.xyz
```
1. Go into SUDO mode
```
su root
```
2. Search and directly install applications updates
```
sudo apt-get update && apt-get upgrade -y
```
3. Search and directly install Debian OS updates
```
sudo apt-get update && sudo apt-get dist-upgrade -y
```
4. Reboot
```
reboot
```

### 