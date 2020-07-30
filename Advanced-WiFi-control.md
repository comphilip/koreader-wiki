* Revamped most actions that require an internet connection to a new/fixed backend that allows forwarding the initial action and running it automatically once connected. (i.e., it'll allow you to set "Action when Wi-Fi is off" to "turn_on", and whatch stuff connect and do what you wanted automatically without having to re-click anywhere instead of showing you a Wi-Fi prompt and then not doing anything without any other feedback).
* Speaking of, fixed the "turn_on" beforeWifi action to, well, actually work. It's no longer marked as experimental.
* Consistently use "Wi-Fi" everywhere.
* On Kobo/Cervantes/Sony, implemented a "Kill Wi-Fi connection when inactive" system that will automatically disconnect from Wi-Fi after sustained *network* inactivity (i.e., you can keep reading, it'll eventually turn off on its own). This should be smart and flexible enough not to murder Wi-Fi while you need it, while still not keeping it uselessly on and murdering your battery.
(i.e., enable that + turn Wi-Fi on when off and enjoy never having to bother about Wi-Fi ever again).
* Made sending `NetworkConnected` / `NetworkDisconnected` events consistent (they were only being sent... sometimes, which made relying on 'em somewhat problematic).
* restoreWifiAsync is now only run when really needed (i.e., we no longer stomp on an existing working connection just for the hell of it).
* We no longer attempt to kill a bogus non-existent Wi-Fi connection when going to suspend, we only do it when it's actually needed.
* Every method of enabling Wi-Fi will now properly tear down Wi-Fi on failure, instead of leaving it in an undefined state.
* Fixed an issue in the fancy crash screen on Kobo/reMarkable that could sometime lead to the log excerpt being missing.
* Worked-around a number of sneaky issues related to low-level Wi-Fi/DHCP/DNS handling on Kobo (see the lengthy comments [below](https://github.com/koreader/koreader/pull/6424#issuecomment-663881059) for details). Fix #6421 
Incidentally, this should also fix the inconsistencies experienced re: Wi-Fi behavior in Nickel when toggling between KOReader and Nickel (use NM/KFMon, and run a current FW for best results).
* For developers, this involves various cleanups around NetworkMgr and NetworkListener. Documentation is in-line, above the concerned functions.

More on this you can find [here.](https://github.com/koreader/koreader/pull/6424).