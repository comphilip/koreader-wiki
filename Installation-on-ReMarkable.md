## SSH into your device

0. Windows users may need to install an [OpenSSH Client](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse#install-openssh-using-windows-settings)
1. Connect your device via USB
2. Find your device password `Menu > Settings > Help > Copyright and Licenses`
3. Open terminal and run: `ssh root@10.11.99.1`

## Installing

### Installation via Toltec

1. SSH into your device and install [Toltec](https://github.com/toltec-dev/toltec#install-it)
2.
    - For reMarkable 1: `opkg install koreader`
    - For reMarkable 2: `opkg install rm2fb koreader`

3. Create a Toltec-compatible service file by running:
```
sed 's|/.*sh|/opt/bin/koreader|' /opt/koreader/koreader.service > /etc/systemd/system/koreader.service
```
4. Launch KOReader:
```
systemctl start koreader
```
- Check for updates from within KOReader as Toltec may not have yet indexed the latest release
- After every reMarkable firmware update, run `toltecctl reenable` and re-run step 3 

### Manual installation

1. Download the [latest release](https://github.com/koreader/koreader/releases) of KOReader
2. Open terminal and navigate to your downloads folder:
```
cd ~/Downloads
```
3. Copy the zip file to your device by running:
```
scp ~/koreader-remarkable-*.zip root@10.11.99.1:
```
4. SSH into your device:
```
ssh root@10.11.99.1
```
5. Unzip the file:
```
unzip ~/koreader-remarkable-*.zip
```
6. Copy the service file to the system directory:
```
cp -v ~/koreader/*.service /etc/systemd/system/
```
7. Install [rm2fb](https://github.com/ddvk/remarkable2-framebuffer#installation) (reMarkable 2 only)
8. Launch KOReader:
```
systemctl start koreader
```

## Launching

### Automatic launch

To launch KOReader at startup, SSH into your device and run:
```
systemctl enable --now koreader && systemctl disable xochitl
reboot
```

### External launcher

Launcher applications such as [oxide](https://github.com/Eeems/oxide), [draft](https://github.com/dixonary/draft-reMarkable) and [remux](https://rmkit.dev/apps/remux) can be installed via [Toltec](https://github.com/toltec-dev/toltec#install-it), for example:
```
opkg install oxide
```

### Middle button launch

To launch KOReader by holding down the middle button for 3 seconds:
```
cp -v /opt/koreader/button-listen.service /etc/systemd/system/
systemctl enable --now button-listen
```

## Optional

### Override System Splashscreens

To use KOReader screensavers for poweroff and reboot events:
```
systemctl disable remarkable-shutdown remarkable-reboot
reboot
```