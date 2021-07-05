## 支持的设备
所有*破解*了的 Kindle 设备均可安装 KOReader。

**注意：** Kindle 设备的越狱能力取决于型号、衍生版本，以及目前运行的固件版本。
详细说明整个过程超出了本文的范围，所以，请在[MobileRead](https://www.mobileread.com/forums/forumdisplay.php?f=150)上查看当前的状况。就目前来说，[这个主题](https://www.mobileread.com/forums/showthread.php?t=320564)比较适合起步。。
一般来说，设备越新就越难搞。

某些小功能目前在非触摸设备上可能仍然不可用，如在 Kindle 4(NT) 和更早的设备上。如果你遇到这样的问题，不要犹豫，提出问题。

## 安装
除了阅读器本身，你还需要安装一个启动器。为此，你可以使用 KPVBooklet 或 KUAL，甚至两者一起，需要注意的是 KPVBooklet 只支持运行固件版本为 5.x 的设备，在最近的固件版本 5.x 上可能无法正常运行;)。

  1. 将你的 Kindle 越狱，参考[本帖](https://www.mobileread.com/forums/showthread.php?t=320564)或其他，这取决于你的设备（见本页面顶部的注意）。
  1. 安装**一个**启动器
      * 安装 KUAL，参考[官方帖子](http://www.mobileread.com/forums/showthread.php?t=203326)。如果你关注过最近任何进展的 JB thread，你可能已经有了:)。
      * 安装 KPV Booklet，参考[这个维基](https://github.com/koreader/kpvbooklet/wiki)。**注意：**KPV 被废弃了，主要是因为无人维护，而且在很多不那么新的固件版本上无法使用。
  1. 安装 KOReader
      1. 阅读[本页末尾的这一节](#err-there-three-kindle-packages-to-choose-from-which-do-i-pick)，弄清楚你要下载哪个 Kindle 版本。
      1. 从[本页面](https://github.com/koreader/koreader/releases)下载最新的专为 Kindle 设计的包。
      1. 解压缩整个压缩文件到 Kindle 的 USB 根目录下
  1. 安装 Stardict 词典（可选）
      * 将 Stardict 格式的字典文件（*.idx, *.ifo, *.dict）复制到 koreader/data/dict 目录。
  1. 安装 Tesseract 语言数据(可选)
      * 将 Tesseract 3.02 的 Tesseract-OCR 语言数据文件（eng.*）复制到 koreader/data/tessdata 目录中。

## 启动
### via KUAL
After installing KOReader, you will see related entries in the KUAL menu. Just tap on it :). The **(no framework)** variants will kill the native GUI first, and restart it once you've quit KOReader (the goal being to gain some more free RAM). Note that said variant may not be completely functional on some model/FW combinations. It's mostly aimed at older devices.


NOTE: After a firmware update, you will most likely have to reinstall some stuff. Of particular importance to KOReader: KPVBooklet itself if you're using it, as well as [KUAL](http://www.mobileread.com/forums/showthread.php?t=203326) itself if you're running the Booklet version. More generally, the [JB Hotfix](https://www.mobileread.com/forums/showpost.php?p=3004892&postcount=1597) is the first thing to try, although current JB versions should ensure basic functionality makes it through. 

### via KOL
There is a [Booklet version](https://github.com/yparitcher/KUAL_Booklet/releases) of KOReader launcher which opens KOReader from Kindle main menu. Default behavior is defined by KOReader -> File Manager -> Top menu, first tab -> Start with (file browser / history / favorites / folder shortcuts / last file). The Booklet must be installed with MR installer.

### via KPV Booklet
Just open any book from the native system, all files except for mobi and txt will be opened with KOReader.

NOTE: On some recent FW versions, KPVBooklet may be non-functional. You may also need a tweaked version of KUAL. Again, check MobileRead's Kindle Dev forum.

NOTE: KPVBooklet may have some issues that don't happen with KUAL:
[Screensaver issues](https://github.com/koreader/koreader/issues/4605), 
[White screen occasionally while reading epub files](https://github.com/koreader/koreader/issues/3287), 
[White screen after waking up](https://github.com/koreader/koreader/issues/4413).


## OTA Update
1. Simply tap the top portion of the device to bring up the menu

2. Tap item in the top right corner

3. Tap update, and follow the on-screen instructions


## 手动安装
根据 [Install section](#Install) 的描述下载最新版，将 **koreader-kindle\*.zip** 或者 koreader-kindle\*.tar.gz** 复制到 kindle 的根目录 (又称 /mnt/us，就是那个能直接看到 `documents` 文件夹的文件夹）。在 kindle 上，选择 KUAL->KOReader->Tools->Update KOReader。 

搞定！

(This calls the script on the kindle */mnt/us/extenstions/koreader/bin/koreader-ext.sh*, which extracts the archive to the koreader folder on the kindle.)

[More information can be found here](https://www.mobileread.com/forums/showthread.php?t=326052)

## USB
**IMPORTANT NOTE:** Switching your device to USBMS mode (by plugging it to a computer over USB) while KOReader is running is *entirely unsupported*, and risks crashing in fun and interesting ways, both KOReader, and possibly the Kindle's underlying system. Recent KOReader versions make an attempt at avoiding complete and utter mayhem, but it's still not recommended to try to test that theory ;).
If you need to charge your device while KOReader is running, either do it with a charger, or switch your device to USBNet mode first.

## Err, 有三个Kindle软件包可供选择，我该选哪个？

它们表明了二进制文件所支持的最早的设备系列（并为之进行了优化）。理想情况下，选择与你的实际设备最接近的那个，获得最佳的性能体验。

* **Legacy**: K2, DX, K3（和它们的衍生版本）
* **Kindle**: K4, K5, PW1
* **PW2**: 其他的，从 PW2 开始（i.e., PW2, KV, KT2, PW3, KOA, KT3, KOA2, PW4, KT4）。


如果你不确定你的确切型号，或者如果这些昵称让你感到困惑，请参考[这个方便的表格](https://wiki.mobileread.com/wiki/Kindle_Serial_Numbers);)。