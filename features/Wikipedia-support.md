Wikipedia lookup function can be invoked at both the dictionary quick lookup window and the highlight menu.

[![Evernote plugin](https://github.com/koreader/koreader/wiki/screenshots/wikipedia_lookup.png)](https://github.com/koreader/koreader/wiki/screenshots/wikipedia_lookup.png)

### Search results with images

![image](https://user-images.githubusercontent.com/24273478/34988036-90df85e0-fabd-11e7-9ab9-464ba397c967.gif)

You can tap on image to see image caption and hold on image to open it in image viewer. More info can be found [here.](https://github.com/koreader/koreader/pull/3609)

### Save wikipedia article as EPUB

You can save wikipedia articles as EPUB files from menu, with optional images. More info [here.](https://github.com/koreader/koreader/pull/2507)

### Tips and tricks

Just like [dictionary](https://github.com/koreader/koreader/wiki/Dictionary-support), wikipedia supports history of searched terms, accessed through menu. More info can be found [here.](https://github.com/koreader/koreader/pull/3549)

You can cancel (too) long, or any, search by tap. More on this [here.](https://github.com/koreader/koreader/pull/3228)

### Changing wikipedia.org domain

To use proxy server like wikipedi0.org tap Extension Menu ->Text Editor and select koreader/frontend/ui/wikipedia.lua . Locate the line consists of `wiki_server = "https://%s.wikipedia.org"`, and change it to url you wish to use. To make sure you didn't delete another text by mistake, tap to "Check Lua" and save changes by "Save". 

[![wiki.gif](https://i.postimg.cc/XNZpn2Pc/wiki.gif)](https://postimg.cc/hhBSr0cf)
