You'll need an SD card.

1. [Install Developer firmware and enable telnet](https://www.mobileread.com/forums/showpost.php?p=3762198&postcount=5).
1. Download [KOReader dependencies](https://www.mobileread.com/forums/attachment.php?attachmentid=169745&d=1550277287)
1. [Download KOReader](https://github.com/koreader/koreader/releases)
1. Copy KOReader and ko-deps-latest.tar.gz to the SD card
1. Insert the SD card on your e-reader and start a telnet connection.
1. Uncompress/install KOReader and KOReader dependencies:
`mv /mnt/sd/ko* /mnt/private
cd /mnt/private
tar -xvf ko-deps.tar.gz
dpkg -i *.deb
unzip koreader-cervantes*.zip`

You can run KOReader from telnet with `/mnt/private/koreader/koreader.sh`.

This will stop the stock reader while KOReader is running and return to it when KOReader exits.

If you are happy with KOReader and want to use it at boot you need to do;
`cp /etc/rc.local /etc/rc.local.backup`
`cp /mnt/private/koreader/koreader-standalone.sh /etc/rc.local`


***
Adapted from [This post on Mobileread](https://www.mobileread.com/forums/showpost.php?p=3760905&postcount=2).