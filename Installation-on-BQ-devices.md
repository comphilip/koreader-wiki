You'll need an SD card.

1. [Install Developer firmware and enable telnet](https://www.mobileread.com/forums/showpost.php?p=3762198&postcount=5).
2. Download [KOReader dependencies](https://www.mobileread.com/forums/attachment.php?attachmentid=167598&d=1541853810)
3. *(Optional)* download a [tool used to enable USB mass storage support on KOReader](https://www.mobileread.com/forums/attachment.php?attachmentid=171942&d=1560706352)
4. [Download KOReader](https://github.com/koreader/koreader/releases)
5. Copy KOReader and dependencies to the SD card
6. Insert the SD card on your e-reader and start a telnet connection.
7. Uncompress/install KOReader and KOReader dependencies:

```bash
mv /mnt/sd/ko* /mnt/private
cd /mnt/private
tar -xvf ko-deps*.tar.gz
dpkg -i *.deb
unzip koreader-cervantes*.zip
```

You can run KOReader from telnet with `/mnt/private/koreader/koreader.sh`.

This will stop the stock reader while KOReader is running and return to it when KOReader exits.

If you are happy with KOReader and want to use it at boot you need to do

```bash
cp /etc/rc.local /etc/rc.local.backup
cp /mnt/private/koreader/koreader-standalone.sh /etc/rc.local
```


***
You can check the entire installation instructions and some device details in [the official post on Mobileread](https://www.mobileread.com/forums/showthread.php?t=311571).