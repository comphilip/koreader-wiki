[Wallabag](https://www.wallabag.org) is a server based _read it later_ tool for web pages.

This plugin downloads the latest articles from a Wallabag server as individual EPUB files.


## Configuration
This is [very likely to change in future](https://github.com/wallabag/wallabag/issues/2800).

The Plugin requires all 4 of `username`, `password`, `Client Id` and `Client Secret`.

`Client Id` and `Client Secret` are generated in the _API Clients Management_ section of your Wallabag server's website.  
They're long (~50 chars each) so you might prefer to save the empty settings and edit the config file directly in your installation directory's `settings/wallabag.lua`.
