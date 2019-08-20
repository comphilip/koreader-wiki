# News downloader 

Retrieves RSS and Atom news entries and saves them as HTML files.

## Introduction

News (RSS/Atom) downloader comes with initial, sample feeds configuration, that can be changed under Settings menu. You can also edit this file in you favorite external text editor.

Entry syntax:
```
{"http://your-url.com", limit=max_number_of_items_to_be_created, download_full_article=true/false},
```

Details:

```
'limit' to "0" means no limit.
'download_full_article=true' - means download full article (may not always work correctly)
'download_full_article=false' - means use only feed description to create feeds (usually only beginning of the article)
'download_full_article' default value is 'true' (if no 'download_full_article' entry)
```

## Download feeds.

All you need to do is copy RSS/Atom url address and use it in News downloader configuration and press “Download news” to start downloading. If successful, once finished, it creates in News downloader directory subfolder for every feed provider.

**Note**: Remember to put coma at the end of each entry!




For more information about RSS/Atom please refer to https://en.wikipedia.org/wiki