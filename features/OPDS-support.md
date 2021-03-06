This plugin adds an OPDS browser to the filemanager, which lets you browse public online OPDS catalogs and download ebooks from these. You can even add your own custom OPDS server. An overview of OPDS catalogs can be found in the [MobileRead Wiki](https://wiki.mobileread.com/wiki/OPDS).

**Note**: In order to access an OPDS catalog search you have to go to file browser (the OPDS catalog button is not available in book reading mode)

[![OPDS catalog](https://github.com/koreader/koreader/wiki/screenshots/screenshot_opds.png)](https://github.com/koreader/koreader/wiki/screenshots/screenshot_opds.png)

[![OPDS catalog](https://github.com/koreader/koreader/wiki/screenshots/screenshot_opds_server.png)](https://github.com/koreader/koreader/wiki/screenshots/screenshot_opds_server.png)



**How to access your own Calibre library on your wifi network using OPDS**
<BR>
<BR>
1 In Calibre:
Connect/Share > Start Content Server
<BR>
-a) Note the address and port
<BR><BR>
2. In KOReader go to Search (magnifying glass) > OPDS Catalog
<BR><BR>
3. Tap on LOCAL CALIBRE LIBRARY (long-press if you wish to edit an existing connection)
<BR><BR>
4. Enter the following:
<BR>
- Calibre host: the address shown in Calibre (at 1a)
- Port: the port (at 1a)
<BR>
5. Tap on LOCAL CALIBRE LIBRARY again. You will see a list of parameters that will match various parameters in your Calibre library - including custom columns you created yourself. 
Eg.<BR>
- By Newest<BR>
- By Title<BR>
- By Authors<BR>
- By Tags<BR>
- By [your custom parameter]<BR>
<BR><BR>
6. By tapping on one of these you will see the books that match that parameter
<BR><BR>
7. Tapping on a book will bring up a dialog to allow you to download it

## Notes

If either of these are running, it is not a problem:
 * KOReader: the wireless connection (via Tools > Connect)
 * Calibre: Connect/Share > 'Wireless device connection'

If Calibre is set to require authentication, it must use "basic" authentication, not "digest" authentication.  Digest authentication is the default for unencrypted communications, but KOReader doesn't support digest authentication.  See [issue #3953](https://github.com/koreader/koreader/issues/3953).  **Warning**: Unencrypted basic authentication is *insecure*.  Anyone who can inspect your network traffic will be able to see your password.  Only use basic authentication with SSL or when it's only run on a completely-trusted network without being exposed to the Internet.