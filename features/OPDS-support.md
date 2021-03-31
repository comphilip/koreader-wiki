This plugin adds an OPDS browser to the filemanager, which lets you browse public online OPDS catalogs and download ebooks from these. You can even add your own custom OPDS server. An overview of OPDS catalogs can be found in the [MobileRead Wiki](https://wiki.mobileread.com/wiki/OPDS).

**Note**: In order to access an OPDS catalog search you have to go to file browser (the OPDS catalog button is not available in book reading mode)

[![OPDS catalog](https://github.com/koreader/koreader/wiki/screenshots/screenshot_opds.png)](https://github.com/koreader/koreader/wiki/screenshots/screenshot_opds.png)

[![OPDS catalog](https://github.com/koreader/koreader/wiki/screenshots/screenshot_opds_server.png)](https://github.com/koreader/koreader/wiki/screenshots/screenshot_opds_server.png)



**How to access your own Calibre library on your wifi network using OPDS**
<BR>

1. In Calibre:
Connect/Share > Start Content Server

- 1a) Note the address and port

2. In KOReader go to Search (magnifying glass) > OPDS Catalog


3. Tap on LOCAL CALIBRE LIBRARY (long-press if you wish to edit an existing connection)


4. Enter the following:
Calibre host:the address shown in Calibre (at 1a)
Port: the port (at 1a)


5. Tap on LOCAL CALIBRE LIBRARY again. You will see a list of parameters that will match various parameters in your Calibre library - including custom columns you created yourself. 
Eg.
By Newest
By Title
By Authors
By Tags
By [your custom parameter]

6. By tapping on one of these you will see the books that match that parameter

7. Tapping on a book will bring up a dialog to allow you to download it

NOTES:
* If either of these are running, it is not a problem:
KOReader: the wireless connection (via Tools > Connect)
Calibre: Connect/Share > 'Wireless device connection'