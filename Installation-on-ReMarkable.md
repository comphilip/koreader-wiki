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
1. SSH into your device and install [Toltec](https://github.com/toltec-dev/toltec#install-it)
2.
    - For reMarkable 1: `opkg install koreader`
    - For reMarkable 2: `opkg install rm2fb koreader`

3. Edit the default service file and copy it to the system directory by running:
```
sed "s|/home/root/koreader/koreader.sh|/opt/bin/koreader|g" /opt/koreader/koreader.service > /etc/systemd/system/koreader.service
```
4. Launch KOReader:
```
systemctl start koreader
```
- Check for updates from within KOReader as Toltec may not have yet indexed the latest release
- To return to Xochitl simply exit KOReader
- reMarkable firmware updates will delete KOReader's systemd units. Run `toltecctl reenable` and step 3 after every firmware update

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

**Warning:** Make sure `systemctl start koreader` works before proceeding!

To launch KOReader at startup, SSH into your device and run:
```
systemctl enable koreader
systemctl disable xochitl
reboot
```

### External launcher

KOReader can be launched by: [oxide](https://github.com/Eeems/oxide), [draft](https://github.com/dixonary/draft-reMarkable) and [remux](https://rmkit.dev/apps/remux). They can installed via [toltec](https://github.com/toltec-dev/toltec#install-it), for example:
```
opkg install oxide
```

### Middle button launch
To launch KOReader by holding down the middle button for 3 seconds, SSH into your device and run:
```
cp -v /opt/koreader/button-listen.service /etc/systemd/system/
systemctl enable --now button-listen
reboot
```

## Optional

### Override System Splashscreens

To use KOReader's screensaver feature for poweroff and reboot events, SSH into your device and run:
```
systemctl disable remarkable-shutdown
systemctl disable remarkable-reboot
reboot
```