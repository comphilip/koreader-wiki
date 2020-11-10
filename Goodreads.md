Allows browsing and searching the Goodreads database of books.

It's located in the 5th tab of the top menu
First you should obtain the developer's key, by going to https://www.goodreads.com/api/keys.  
After you fill in "Application name" and "Company name" fields, you click "update app info" button.  
At the top of the page, you'll find your `key` and `secret` values. You need to enter them in the Goodreads Plugin.  
If you don't want to type it by hand, you can first enter some "dummy" values, connect your e-reader to PC and paste them in their respective place in `<koreader's directory>/settings/goodreadssettings.lua`.

The file's contents will looks something like that
```lua
-- we can read Lua syntax here!
return {
    ["goodreads"] = {
        ["key"] = "dummy",
        ["secret"] = "dummy"
    }
}
```

Currently the plugin doesn't allow marking the books as `Read`