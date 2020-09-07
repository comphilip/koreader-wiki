## General

When connected to WiFi you can find the IP address and root password for your
reMarkable in Settings -> About, then scroll down the GPLv3 compliance on the
right (finger drag scroll, not the page forward/back buttons). This should also
work for the USB network you get if you connect the reMarkable to your computer
with a USB cable.

## Install

- Download and install the latest [release](https://github.com/koreader/koreader/releases) of KOReader.

   ```
   scp koreader-remarkable-*.zip root@IP:
   ssh root@IP
   unzip koreader-remarkable-*.zip
   ```
- Set up to launch from long press on middle button:
   ```
   cp -v koreader/*.service /etc/systemd/system/
   systemctl enable --now button-listen
   ```
   Some reMarkable software updates will wipe the new systemd units so you will have
   to run these two steps again when that happens.
- Or you could set up to launch via swipe gesture that triggers the Draft launcher.
   1. Install reMarkable [touchgestures](https://github.com/ddvk/remarkable-touchgestures)
   2. Install reMarkable [autoinstall](https://github.com/ddvk/remarkable-autoinstall)
   3. Create a draft launcher entry in the /home/root/.config/draft subdirectory; create a file called eg 05-koreader (the number determines 
   where the entry appears in the menu sort order).
   ```
   name=koreader
   desc=EBook reader
   call=/home/root/koreader/koreader.sh
   term=:
   ```
## Launch with middle button

Hold down the middle button for 3 seconds to start koreader. To return to
xochitl just exit koreader (swipe down from the top of the screen, select icon
in the top right, Exit, Exit).

## Launch with upwards swipe
Press two fingers against the screen 10-12 cm apart to activate the touchgesture module, then swipe up with one finger from bottom of screen.  The draft launcher menu should now appear. You can start koreader or any other app configured to appear in the draft menu. To return to draft launcher just exit koreader (swipe down from the top of the screen, select icon in the top right, Exit, Exit). To return to xochitl from the draft launcher menu swipe up from the bottom of the screen.

