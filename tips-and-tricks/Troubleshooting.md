### 1. My Kindle keeps "rebooting" after some page turns in reflowing mode for some PDF files.
A: The Kindle devices have limited free RAM leaving for Koreader. And reflowing requires heavy image manipulation which is memory demanding especially when font size is set too large. And background rendering (hinting) may take up last bit of spare RAM. One solution to this problem is decreasing default hinting page number to restrain background rendering activity. For more info about setting hinting number please refer the `DHINTCOUNT` entry in [[Change defaults]].

### 2. change you screenshot save directory (改变Koreader截屏保存位置）
A: modify in the screenshoter.lua file ,which location is /koreader/frontend/ui/widget/.
