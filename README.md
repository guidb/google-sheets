
<p align = "center" >
    <img src="https://github.com/azkadev/azkadev/blob/main/pp.png?raw=true" width="350" height="350" />
</p >

<p align="center">
    <a href="https://github.com/azkadev"><img title="Author" src="https://img.shields.io/badge/AUTHOR-AZKADEV-orange.svg?style=for-the-badge&logo=github"></a>
</p>

<p align="center"> 
<a href="https://www.buymeacoffee.com/" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-blue.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>
</p>

<p align="center">
<a href="https://t.me/azkadev"><img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Ft.me%2F%40azkadev&count_bg=%234AA803&title_bg=%231C1C1C&icon=telegram.svg&icon_color=%23FFFFFF&title=Telegram&edge_flat=false"/></a>
<a href="https://tiktok.com/@azkadev"><img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fwww.tiktok.com%2F%40azkadev&count_bg=%234AA803&title_bg=%231C1C1C&icon=tiktok.svg&icon_color=%23FFFFFF&title=Tiktok&edge_flat=false"/></a>
<a href="https://github.com/azkadev"><img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2F%40azkadev&count_bg=%232300CB&title_bg=%23663838&icon=github.svg&icon_color=%23FFFFFF&title=Github&edge_flat=false"/></a>
<a href="https://instagram.com/azkadev"><img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Finstagram.com%2F%40azkadev&count_bg=%237C62F6&title_bg=%23663838&icon=instagram.svg&icon_color=%23FFFFFF&title=Instagram&edge_flat=false"/></a>
 <a href="https://www.youtube.com/channel/UC74N8oC9ow7PK-G8XfWVbcA"><img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Finstagram.com%2Fazkadev&count_bg=%237C62F6&title_bg=%23EB0000&icon=youtube.svg&icon_color=%23FFFFFF&title=Youtube&edge_flat=false"/></a> 
</p>

---

## ❄Content-Library
- 📰 0% Ads
- 💸 0% Tracker
- 📃 0% Logging

## ❄Docs 

1. **Get All** 
		```getAll(range_name)```
		example
		
![](https://github.com/guidb/google-sheets/blob/main/ss/dbsheet.png?raw=true)

```js
const { googleSheets } = require("google-sheets")
async function test() {
  var db = new googleSheets("your_sheet_id", "credentials.json")
  var range_name = "Sheet1!A2:Z";
  var data = await db.getAll(range_name)
  console.log(JSON.stringify(data, null, 2))
}

test()
//--! Result log here !--\\
/*
[
  [
    "12345",
    "azkadev",
    "azka"
  ],
  [
    "123456",
    "devano",
    "devan",
    "alaska"
  ],
  [
    "1234567",
    "",
    "farel",
    "farel"
  ]
]
*/
```		
![](https://github.com/guidb/google-sheets/blob/main/ss/dbsheet.png?raw=true)

2. **Get getRow** 
		```db.getRow(range_name, user_data, get_row_num, return_row_number)```
		example
```js
const { googleSheets } = require("google-sheets")
async function test() {
  var db = new googleSheets("your_sheet_id", "credentials.json")
  var range_name = "Sheet1!A2:Z"; //--! fil your range_name !--\\
  var user_data = "12345" //--! fill find data !--\\
  var get_row_num = 0 //--! the data is 0 because it is in range a, if b is 1 and next !!--\\
  var return_row_num = 1 //--! retur row b if you want c fill 2 next... !--\\
  var data = await db.getRow(range_name,user_data, get_row_num, return_row_num)
  console.log(JSON.stringify(data, null, 2))
}

test()
//--! Result log here !--\\
/*
"azkadev"
*/
```

![](https://github.com/guidb/google-sheets/blob/main/ss/dbsheet.png?raw=true)

3. **Get getRows** 
		```getRows(range_name, user_data, get_row_num)```
		example
```js
const { googleSheets } = require("google-sheets")
async function test() {
  var db = new googleSheets("your_sheet_id", "credentials.json")
  var range_name = "Sheet1!A2:Z";
  var user_data = "12345"
  var get_row_num = 0
  var data = await db.getRows(range_name,user_data, get_row_num)
  console.log(JSON.stringify(data, null, 2))
  console.log(JSON.stringify(data, null, 2))
}

test()
//--! Result log here !--\\
/*
{
  "0": "12345",
  "1": "azkadev",
  "2": "azka"
}
*/
```
Before 

![](https://github.com/guidb/google-sheets/blob/main/ss/dbsheet.png?raw=true)

After  

![](https://github.com/guidb/google-sheets/blob/main/ss/dbsavesheet.png?raw=true)

4. **save** 
		```save(range_name, user_data, array_save, array_update, range_name_update) ```
		example
```js
const { googleSheets } = require("google-sheets")
async function test() {
  var db = new googleSheets("your_sheet_id", "credentials.json")
  var array_save = [ "data1", "data 2", "data 3" ]
  var array_update = [ "data1", "data 2 update", " data 3", "new data" ]
  var range_name = "Sheet1!A2:Z";
  var range_name_update = "Sheet1!A:Z"
  var data = await db.save(range_name, array_save[0], array_save, array_update, range_name_update)
  console.log(JSON.stringify(data, null, 2))
}

test()
//--! Result log here !--\\
/*
true
*/
```

Before 

![](https://github.com/guidb/google-sheets/blob/main/ss/dbsavesheet.png?raw=true)

After

![](https://github.com/guidb/google-sheets/blob/main/ss/dbsaverow.png?raw=true)

5. **saverow** 
		```saveRow(range_name, user_data, get_row_num, new_data, range_name0)```
		example
```js
const { googleSheets } = require("google-sheets")
async function test() {
  var db = new googleSheets("your_sheet_id", "credentials.json")
  var range_name = "Sheet1!A2:Z";
  var range_name_update = "Sheet1!A:Z"
  var data = await db.saveRow(range_name, 123456, 0, "gibran", "Sheet1!C")
  console.log(JSON.stringify(data, null, 2))
}

test()
//--! Result log here !--\\
/*


*/
```
Before

![](https://github.com/guidb/google-sheets/blob/main/ss/dbsaverow.png?raw=true)

After

![](https://github.com/guidb/google-sheets/blob/main/ss/dbsaverows.png?raw=true)

6. **saverows** 
		```saveRows(range_name, user_data, get_row_num, new_data_array, range_name_update, range_name_update0)```
		example
```js
const { googleSheets } = require("google-sheets")
async function test() {
  var db = new googleSheets("your_sheet_id", "credentials.json")
  var range_name = "Sheet1!A2:Z";
  var data = await db.getRow(range_name, user_data, get_row_num, return_row_number)
  console.log(JSON.stringify(data, null, 2))
}

test()
//--! Result log here !--\\
/*


*/
```

## ❄To-Do
A list that i should do more for this project...

- ✔ crud
- 🔜 clone  
- 🔜 diagram  

## 🖥Requirements
- Node v10+ (Node v14 Recommended)
- Network connection

---
