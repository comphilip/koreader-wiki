## SSH into your device

0. Windows users will need to install an [OpenSSH Client](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse#install-openssh-using-windows-settings). MacOS and Linux users need no extra software.
1. Connect your device via USB
2. Find your device password `Menu > Settings > Help > Copyright and Licenses`
3. Open terminal and run:
```
ssh root@10.11.99.1
```

## Installing

### Installation via Toltec
1. SSH into your device and install [toltec](https://github.com/toltec-dev/toltec#install-it)
2. For reMarkable 1:
```
opkg install koreader
```
3. For reMarkable 2:
```
opkg install rm2fb koreader
```
4. Edit the default service file to be toltec-compatible:
```
sed -i "s|/home/root/koreader/koreader.sh|/opt/bin/koreader|g" /opt/koreader/koreader.service
```
5. Copy the service file to the system directory:
```
cp -v /opt/koreader/koreader.service /etc/systemd/system/
```
6. Launch KOReader:
```
systemctl start koreader
```
- **Note:** Check for updates from within KOReader as toltec may not have yet indexed the latest release.
- **Note:** reMarkable firmware updates will delete KOReader's systemd units. Run `toltecctl reenable` and repeat steps 4 and 5 after every firmware update

### Manual installation
1. Download the [latest release](https://github.com/koreader/koreader/releases) of KOReader
2. Open terminal and navigate to your downloads folder:
```
cd Downloads
```
3. Copy the zip file to your device by running:
```
scp koreader-remarkable-*.zip root@10.11.99.1:
```
4. SSH into your device and unzip the file:
```
unzip koreader-remarkable-*.zip
```
5. Copy the service file to the system directory:
```
cp -v koreader/koreader.service /etc/systemd/system/
```
6. reMarkable 2 users must install [rm2fb](https://github.com/ddvk/remarkable2-framebuffer#installation)
7. Launch KOReader:
```
systemctl start koreader
```

## Launching

### Automatic launch
**Warning:** Make sure KOReader starts successfully before configuring the automatic launch. If both `xochitl` and `koreader` are disabled, your device will be stuck at "reMarkable is starting". Keep a copy of your password in case you need to troubleshoot.

1. SSH into your device and run:
```
systemctl disable xochitl
systemctl enable koreader
```
2. Reboot your device
- To return to Xochitl simply exit KOReader

### Launch with external launcher

KOReader is supported by the following launchers: [oxide](https://github.com/Eeems/oxide), [draft](https://github.com/dixonary/draft-reMarkable) and [remux](https://rmkit.dev/apps/remux). They can installed via [toltec](https://github.com/toltec-dev/toltec#install-it) e.g. `opkg install oxide`.

### Launch with middle button
1. SSH into your device and run:
```
cp -v /opt/koreader/button-listen.service /etc/systemd/system/
systemctl enable --now button-listen
```
2. Reboot your device
3. While using Xochitl, hold down the middle button for 3 seconds to start KOReader

## Optional

### Override System Splashscreens

To use KOReader's screensaver feature for poweroff and reboot events:

1. SSH into your device and run:
```
systemctl disable remarkable-shutdown
systemctl disable remarkable-reboot
```
2. Reboot your device