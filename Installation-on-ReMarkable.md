## Installation via Toltec

1. Install [Toltec](https://github.com/toltec-dev/toltec/tree/stable#install-it)
2. Run: 
```
opkg install koreader
```

- You may also install a [launcher](https://toltec-dev.org/stable/)

## Manual installation

0. Install [rm2fb](https://github.com/ddvk/remarkable2-framebuffer#installation) (reMarkable 2)
1. Download the [latest release](https://ota.koreader.rocks/) of KOReader
2. Copy the file to your device:
```
scp koreader-remarkable-*targz root@10.11.99.1:
```
4. Log into your device:
```
ssh root@10.11.99.1
```
5. Extract the contents of the file:
```
tar -xf /home/root/koreader-remarkable-*targz
```
6. Copy the systemd unit file to the system directory:
```
cp /home/root/koreader/*service /etc/systemd/system/
```
7. Launch KOReader:
```
systemctl start koreader
```
- To launch KOReader by holding down the middle button for 3 seconds (reMarkable 1):
```
systemctl enable --now button-listen
```
- To launch KOReader at startup:
```
systemctl disable --now xochitl && systemctl enable --now koreader
```
- To override reMarkable's splashscreens for poweroff and reboot events:
```
systemctl disable remarkable-shutdown remarkable-reboot
```