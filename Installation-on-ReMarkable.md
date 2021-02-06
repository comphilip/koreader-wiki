## Finding your IP and password

1. Connect your device via USB.
2. Navigate to "Menu > Settings > Help > Copyright and Licenses".
3. Under "GPLv3 Compliance" you will find your username ("root"), your password and your IP ("10.11.99.1").

## Installation

0. Windows users will need to enable the OpenSSH client. Mac OS and Linux users need no extra software.
1. Download the [latest release](https://github.com/koreader/koreader/releases) of KOReader.
2. Open terminal and copy the zip file to your device by running:
   `scp koreader-remarkable-*.zip root@10.11.99.1:`
3. Log into your device and unzip the file:
   ```
   ssh root@10.11.99.1
   unzip koreader-remarkable-*.zip
   ```
4. Copy the service file to the system directory and reload all units:
   ```
   cp -v koreader/koreader.service /etc/systemd/system/
   systemctl daemon-reload
   ```
5. If your device is reMarkable 2, you will need to install [rm2fb](https://github.com/ddvk/remarkable2-framebuffer) first.
6. Launch KOReader:
   `systemctl start koreader`

## Launching methods

### Automatic launch
**WARNING:** Only do this if you are sure you know what you are doing, and ensure that koreader is working correctly before configuring automatic launch

1. While ssh'd into the device, run:
   ```
   systemctl disable xochitl
   systemctl enable koreader
   ```
2. Reboot your device:\
`reboot`
3. KOReader will replace Xochitl as the program launched at boot.
- To return to xochitl simply exit KOReader or run `systemctl start xochitl`.
- **Note:** This method is [not supported](https://github.com/koreader/koreader/issues/7076) on reMarkable 2. On ReMarkable 1, make sure at least one service is enabled. If both `xochitl` and `koreader` are disabled, your device will become stuck at "reMarkable is starting" screen.
### Launch with middle button

1. Copy and enable the button-listen service file:
   ```
   cp -v koreader/button-listen.service /etc/systemd/system/
   systemctl enable --now button-listen
   ```
2. Reboot your device.
3. Hold down the middle button for 3 seconds to start KOReader.
- To return to xochitl simply exit KOReader.
- **Note:** ReMarkable firmware updates will wipe KOReader's systemd units so you will have to run `cp -v koreader/*.service /etc/systemd/system/` again after every update.

### Launch with external launcher
KOReader is supported by launchers such as: [oxide](https://github.com/Eeems/oxide/releases), [draft](https://github.com/dixonary/draft-reMarkable) and [remux](https://rmkit.dev/apps/remux).

Steps to launch KOReader via the draft's swipe gesture:
1. Install reMarkable [touchgestures](https://github.com/ddvk/remarkable-touchgestures).
2. Install reMarkable [autoinstall](https://github.com/ddvk/remarkable-autoinstall).
3. Create a draft launcher entry in the `/home/root/.config/draft` subdirectory and within it create a file called `eg 05-koreader` (the number determines where the entry appears in the menu sort order):
   ```
   name=koreader
   desc=EBook reader
   call=/home/root/koreader/koreader.sh
   term=:
   ```
4. Press two fingers against the screen 10-12 cm apart to activate the touchgesture module.
5. Swipe up with one finger from the bottom of the screen. The draft launcher menu should now appear.
6. You can start koreader or any other app configured to appear in the draft menu.
- To return to draft launcher just exit koreader (swipe down from the top of the screen > Top right icon > Exit > Exit).
- To return to xochitl from the draft launcher menu swipe up from the bottom of the screen.