# Cover image

Saves the cover image of the current book in a file

## Introduction

This plugin works as a workaround to solve the lack of support for screensaver in android e-ink devices. While it can be useful in other brands it was tested on **Tolinos** only.

When you have a book opened, you can find the plugin in the menu `Gear->Screen->Save cover image`

There you can 
1. enter the filename to save the cover image.
2. enable the creation of the file on every opening of a book.
3. exclude saving certain books covers.
4. enter the filename of a fallback image.
5. turn the fallback on, if a book is closed or KOReader is quit.

## Sample usage on Tolinos
Tolinos can use a file to show a user supplied **suspend** image. So, if you set the cover image filename to that suspend image you can have your books cover as screensaver.

The name of the suspend image is something like `suspend.jpg` or `suspend_others.jpg`, depending on your firmware and hardware:

`suspend_others.jpg` on an Epos 2 with FW 14.0.0 and 14.0.1

`suspend_others.jpg` on a Vision 4HD with FW 13.2.1

`suspend.jpg` on an Epos 1 with FW 13.2.1 (reported by rola25)

`suspend.jpg` on a Vision 4HD FW < 11.2.2

Before you play with the `Save cover image` in KOReader you should check the functionality of the suspend image:
1. Connect your Tolino with your computer.
2. Mount and open you Tolino on your computer. You should see at least the folders `Books` and `koreader`.
3. Copy a JPG image to that folder and rename it.
4. Unplug you Tolino.
5. Put your Tolino to sleep. 
6. If you see your image, you know the right suspend image name, if not go to 1.

(If you don't find a correct filename, you can try to find a filename on `/storage/sdcard1` with `logcat`, when you put your Tolino to sleep.)

After you have found out the correct name for your suspend image you can enter it in `Set system screensaver image` with the correct path: On my Epos2 the correct name would be `/sdcard/suspend_others.jpg`.

You can also use a user supplied fallback image on `/sdcard`.

**NOTE1:** Root is **not** needed.

**NOTE2:** The image is only shown, when the Tolino **is not connected via USB**.

## Onyx Boox devices:
1. Go to `Screen -> Save cover image`
2. Select `Save book cover`
3. Select `Set system screensaver image`
4. Set path to: /sdcard/Pictures/<insert any name here>.png
5. In the boox software go to `Storage -> Pictures`
6. Right click your file -> Set as screensaver
7. Confirm any dialogs that pop up

Since now, whatever book you open last in KOReader should end up as a screensaver. For more information see [this issue](https://github.com/koreader/koreader/issues/6876#issuecomment-727527509).