## SSH Login

1. Connect your device via USB
2. Find your device password: Menu > Settings > Help > Copyright and Licenses
3. Open terminal and run:
```
ssh root@10.11.99.1
```

## Installation via Toltec

1. Connect your device to Wi-Fi and install [Toltec](https://github.com/toltec-dev/toltec/tree/testing#install-it)
5. Download and install KOReader: 
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
tar -xf ~/koreader-remarkable-*targz
```
6. Copy the systemd unit file to the system directory:
```
cp ~/koreader/*service /etc/systemd/system/
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
systemctl enable --now koreader && systemctl disable --now xochitl
```
- To override reMarkable's splashscreens for poweroff and reboot events:
```
systemctl disable remarkable-shutdown remarkable-reboot
```