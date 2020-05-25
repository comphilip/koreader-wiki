With Calibre Companion plugin you can send documents from your Calibre library directly to your KOReader devices via Wifi connection.

To use this plugin you need to keep your PC that runs Calibre and your KOReader device in one local network usually in one router. Then start your Calibre wireless device connection as the following screenshot shows:
[![Start calibre wireless connection](https://github.com/koreader/koreader/wiki/screenshots/calibre_companion_start.png)](https://github.com/koreader/koreader/wiki/screenshots/calibre_companion_start.png)

Use the default option in the popup window should be OK as for Calibre version 2.2.

After the calibre wireless device connection is established (the red indicator of the connection button changes into green), go to the plugin tab of KOReader and select "connect" option in the "Calibre Companion" plugin. If all things go right Koreader should say "Connected to Calibre Server at _somehost:someport_" and your Calibre should recognize KOReader as a wireless device like this:
[![Connected calibre server](https://github.com/koreader/koreader/wiki/screenshots/calibre_companion_connected.png)](https://github.com/koreader/koreader/wiki/screenshots/calibre_companion_connected.png)

You can send one or more documents to your Koreader device from your Calibre library now:
[![Send documents to KOReader](https://github.com/koreader/koreader/wiki/screenshots/calibre_companion_send.png)](https://github.com/koreader/koreader/wiki/screenshots/calibre_companion_send.png)

Note that if it's the first time you run Calibre Companion plugin, you may be prompted to choose the "Inbox" directory in which the received documents will be saved.

### Calibre and keeping books on internal and external storage

If you want to use calibre and have books both on internal and external memory, you need to set Koreader to know how to access both places.

This is done via the defaults.lua system (or, defaults.persistent.lua, which survives manual updates, so best to use it instead defaults.lua, to create it, just copy already existing defaults.lua to persistent.defaults.lua and afterwards edit new setting in it). In particular the section about SEARCH_LIBRARY_PATH

If you actively use both storage locations with Calibre, you'll probably want to use something like:

SEARCH_LIBRARY_PATH  = "/mnt/onboard"

SEARCH_LIBRARY_PATH2 = "/mnt/sd"

(make sure to use correct path)