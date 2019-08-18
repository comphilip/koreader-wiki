- For distributions based on Debian/Ubuntu:

Download the `.deb` package for your computer architecture, `x86_64` when in doubt.
Install it from your package manager or from the commandline with `dpkg -i koreader*.deb`

- For generic distributions (x86_64):

Download the `AppImage` and make it executable with `chmod +x koreader*.appImage`
Execute it with `./koreader*.appImage`

## So what is this “AppImage”?

Simply put, it's a portable app for Linux, which has been a long-standing request (#1417). After you download the file, you'll first need to allow it to run as a program. You can do so by right clicking in your file manager, choosing `Properties` → `Permissions` and checking the box that reads `Allow this file to run as a program` or something equivalent. If you prefer to use the terminal, run `chmod +x koreader-appimage-x86_64-linux-gnu-v2015.11-1644-ge39ed90_2018-04-09.AppImage`.

The AppImage is a release version of what we KOReader developers call “the emulator.” It has existed since all the way back in 2011 to ease the development process. You can drag and drop a file onto the window to open it, there's a titlebar that indicates the currently opened file, and a basic albeit imperfect form of window resizing.

Because the AppImage is built on top of the emulator, you can set default window sizes and DPI through the command line. `EMULATE_READER_W=2000 EMULATE_READER_H=1500 EMULATE_READER_DPI=180 ./koreader-appimage-x86_64-linux-gnu-v2015.11-1644-ge39ed90_2018-04-09.AppImage`. You could also try out other debugging aids such as `EMULATE_READER_FLASH=100`. There's also another more practical use besides just reading documents: you could use the AppImage to verify whether a bug is specific to your device or if it's inherent in the program.

The desktop version of KOReader implements game controller support (#3819). The control scheme is depicted below, and you can use it in the AppImage. It's currently equivalent to the functionality offered by the Kindle 4NT. It might sound slightly odd, but it's rather nice to just lean back with a gamepad while having some document on your screen.

<kbd><img src=https://user-images.githubusercontent.com/202757/38541203-a50d455c-3c9e-11e8-9cb0-de21cda0ca0e.png width=70%></kbd>

|   | Gamepad button             | Action                                      |
|---|----------------------------|---------------------------------------------|
| 1 | Left stick & d-pad         | Arrow keys (menu navigation)                |
| 2 | Right stick                | Page up & down                              |
| 3 | A button                   | Press/enter (also opens bottom reader menu) |
| 4 | B button                   | Escape/back                                 |
| 5 | Left bumper                | Page up                                     |
| 6 | Right button               | Page down                                   |
|   | Start/Menu button (not shown) | Open menu                                   |
