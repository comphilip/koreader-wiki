The "Statistics" plugin provides you information about your performance reading. 
The plugin has setting for two properties MIN (by default is 5) and MAX (by default is 90) seconds. If you read curent page in range between MIN and MAX seconds, information about time and page will be added into statistics. Otherwise the plugin will skip info about time and page. You can change both properties in settings.

The plugin doesn't work with PDF, DjVu and CBZ formats. 

By default the plugin is enabled. 

### The plugin provides next counters

For current book:
* Current period of reading
* Time to Read
* Total time
* Total highlights
* Total notes
* Average time per page
* Read pages/Total pages

Total:
* All time (for all books)
* Time for particular book

You can tap on book title and see detailed information:
* Count of pages and total time by days

### Some pictures
![plugins](https://cloud.githubusercontent.com/assets/220872/9965401/bbcd7230-5e3e-11e5-98bb-30b58c08d9b4.png)

![Current](https://cloud.githubusercontent.com/assets/220872/9731982/132848ca-5629-11e5-8fd5-b72fde1022b5.png)

![Total](https://cloud.githubusercontent.com/assets/220872/9732033/4cccd17c-5629-11e5-84a6-b359c864e62d.png)

![Details](https://cloud.githubusercontent.com/assets/220872/9732112/dcf92be2-5629-11e5-8827-58e66dccb830.png)


### For developers
The data stored into folder "statistics". File name is based on book title and has extension ".stat" 
The structure of file

```javascript
return {
    ["total_time"] = 29467,
    ["authors"] = "Николай А. Островский",
    ["title"] = "Как закалялась сталь",
    ["highlights"] = 0,
    ["notes"] = 0,
    ["details"] = {
        [1] = {
            ["read"] = 8,
            ["time"] = 1425168796,
            ["page"] = 3
        },
        [2] = {
            ["read"] = 63,
            ["time"] = 1425168872,
            ["page"] = 9
        },
        [3] = {
            ["read"] = 39,
            ["time"] = 1425168911,
            ["page"] = 10
        }
         } 
    ["series"] = "",
    ["language"] = "ru"
}
```

The structure of item in details

```javascript
["read"] = 39 //seconds spent on page
["time"] = 1425168911 //date
["page"] = 10 //read page
```