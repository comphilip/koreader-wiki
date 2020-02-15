## General

When connected to WiFi you can find the IP address and root password for your
reMarkable in Settings -> About, then scroll down the GPLv3 compliance on the
right (finger drag scroll, not the page forward/back buttons). This should also
work for the USB network you get if you connect the reMarkable to your computer
with a USB cable.

## Install

- Download the latest [release](https://github.com/koreader/koreader/releases) of KOReader.

   ```
   scp koreader-remarkable-*.zip root@IP:
   ssh root@IP
   unzip koreader-remarkable-*.zip
   cp -v koreader/*.service /etc/systemd/system/
   systemctl enable --now button-listen
   ```

## Launch

Hold down the middle button for 3 seconds to start koreader. To return to
xochitl just exit koreader (swipe down from the top of the screen, select icon
in the top right, Exit, Exit).

Some reMarkable software updates will wipe the new systemd units so you will have
to run the last two steps again when that happens.