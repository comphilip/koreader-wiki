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

### Installation via Toltec
1. SSH into your device and install [Toltec](https://github.com/toltec-dev/toltec#install-it)
2. For reMarkable 1 run: 
    ```
    opkg install koreader
    ```
3. For reMarkable 2 run:
    ```
    opkg install rm2fb koreader
    ```
4. Make sure the service was [configured correctly](https://github.com/koreader/koreader/issues/7494#issuecomment-812888641)
5. Launch KOReader:
    ```
    systemctl start koreader
    ```
- KOReader will be installed to `/home/root/.entware/koreader` and mounted to `/opt/koreader`
- You may want to check for updates from within KOReader as Toltec may not have indexed the [latest release](https://github.com/koreader/koreader/releases) yet

### Manual installation
1. Download the [latest release](https://github.com/koreader/koreader/releases) of KOReader
2. Copy the zip file to your device by running:
   ```
   scp koreader-remarkable-*.zip root@10.11.99.1:
   ```
3. SSH into your device and unzip the file:
   ```
   unzip koreader-remarkable-*.zip
   ```
4. Copy the service file to the system directory and reload all units:
   ```
   cp -v koreader/koreader.service /etc/systemd/system/
   systemctl daemon-reload
   ```
5. reMarkable 2 users must install [rm2fb](https://github.com/ddvk/remarkable2-framebuffer)
6. Launch KOReader:
    ```
    systemctl start koreader
    ```
- KOReader will be installed to `/home/root/koreader`

## Launching

### Automatic launch
**Warning:** Make sure KOReader starts successfully before configuring the automatic launch
1. SSH into your device and run:
   ```
   systemctl disable xochitl
   systemctl enable koreader
   ```
2. Restart your device by running:
    ```
    reboot
    ```
3. KOReader will replace Xochitl as the program launched at boot
- To return to Xochitl simply exit KOReader or run `systemctl start xochitl`
- **Note:** Make sure at least one service is enabled. If both `xochitl` and `koreader` are disabled, your device will become stuck at "reMarkable is starting"

### Launch with external launcher
KOReader is supported by [oxide](https://github.com/Eeems/oxide), [draft](https://github.com/dixonary/draft-reMarkable) and [remux](https://github.com/rmkit-dev/rmkit/tree/master/src/remux). The example below uses oxide:
1. Install [Toltec](https://github.com/toltec-dev/toltec#install-it)
2. SSH into your device and run:
    ```
    opkg install oxide
    ```
3. Reboot your device
4. Tap on KOreader from the oxide menu

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