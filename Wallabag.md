[Wallabag](https://www.wallabag.org) is a server based _read it later_ tool for web pages.

This plugin downloads the latest articles from a Wallabag server as individual EPUB files.


## Configuration
This is [very likely to change in future](https://github.com/wallabag/wallabag/issues/2800).

The Plugin requires all 4 of `username`, `password`, `Client Id` and `Client Secret`. You must set the download directory as well. 

`Client Id` and `Client Secret` are generated in the _API Clients Management_ section of your Wallabag server's website. The `Redirect URIs` which is optional should be empty.

The `Client Id` and `Client Secret` are long (~50 chars each) so you might prefer to save the empty settings and edit the config file directly in your installation directory's `settings/wallabag.lua`. Triple check the `username`, `password`, `Client Id` and `Client Secret` as the variable names are very similar looking and can be confusing. 

On certain legacy devices saving empty settings may not be possible, in that case you can add and modify the following settings, directly in your installation directory's `settings/wallabag.lua`. 
```
-- we can read Lua syntax here!
return {
    ["wallabag"] = {
        ["articles_per_sync"] = 30,
        ["download_queue"] = {},
        ["filter_tag"] = "",
        ["ignore_tags"] = "",
        ["is_archiving_deleted"] = false,
        ["is_auto_delete"] = false,
        ["is_delete_finished"] = true,
        ["is_delete_read"] = false,
        ["is_sync_remote_delete"] = false,
        ["remove_finished_from_history"] = false,
        ["server_url"] = "",
        ["client_id"] = "",
        ["client_secret"] = "",
        ["username"] = "",
        ["password"] = "",
        ["directory"] = "",
    },
}
```