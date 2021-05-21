**This page is about Remarkable 1. For the status of Remarkable 2 support, see https://github.com/koreader/koreader/issues/6792**

## SSH into your device

0. Windows users will need to install an [OpenSSH Client](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse#installing-openssh-from-the-settings-ui-on-windows-server-2019-or-windows-10-1809). Mac OS and Linux users need no extra software.
1. Connect your device via USB
2. Navigate to `Menu > Settings > Help > Copyright and Licenses`
3. Under "GPLv3 Compliance" you will find your username `root`, your IP `10.11.99.1` and your password
4. Open terminal and run:
```
ssh root@10.11.99.1
```

## Installing

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
5. Copy the service file to the system directory::
```
cp -v koreader/koreader.service /etc/systemd/system/
```
6. reMarkable 2 users must install [rm2fb](https://github.com/ddvk/remarkable2-framebuffer)
7. Launch KOReader:
```
systemctl start koreader
```

## Launching

### Automatic launch
**Warning:** Make sure KOReader starts successfully before configuring the automatic launch
1. SSH into your device and run:
```
systemctl disable xochitl
systemctl enable koreader
```
2. Reboot your device
- To return to Xochitl simply exit KOReader
- **Note:** Make sure at least one service is enabled. If both `xochitl` and `koreader` are disabled, your device will become stuck at "reMarkable is starting"

### Launch with middle button
1. SSH into your device and run:
```
cp -v koreader/button-listen.service /etc/systemd/system/
systemctl enable --now button-listen
```
2. Reboot your device
3. Hold down the middle button for 3 seconds to start KOReader
- To return to Xochitl simply exit KOReader
- **Note:** reMarkable firmware updates will delete KOReader's systemd units so you will have to run `cp -v koreader/*.service /etc/systemd/system/` again after every update

## Optional

### Override System Splashscreens

To use KOReader's screensaver feature for poweroff and reboot events:

1. SSH into your device and run:
```
systemctl disable remarkable-shutdown
systemctl disable remarkable-reboot
```
2. Reboot your device