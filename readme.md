# 短网址服务

简单的短网址服务，支持自定义别名和随机别名。

## 注意事项 注意事项 注意事项
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
！！！！！！！特别注意！！！！！原版由于express  版本迭代 剥离了 body-parser  所以需要做如下更改！！！！！

将原先的代码

var express = require('express');
var app = express();
app.use(express.bodyParser());
改为

var express = require('express');
var bodyParder = require('body-parser');
var app = express();
app.use(express.urlencoded({ extended: true }))

***********************************************************************************************************************************************
package.json 更新为如下所示！！！！！

{
  "name": "shorturl",
  "version": "0.0.1",
  "main": "index.js",
  "dependencies": {
    "body-parser": "^1.20.0",
    "express": "",
    "querystring": "",
    "url": ""
  }
}
*******************************************************************************************************************************************************
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


## 安装

```
npm install
```

## 用法

**启用服务** 

```
node index
```

**get模式获取随机别名** 以获取`http://google.com/`的别名为例

```
http://localhost:8088/url?url=http://google.com/
```

**get方式存储自定义别名** 

```
http://localhost:8088/define?origin=http://google.com/&alias=google
```

## LICENSE

MIT

## 日期
2022/06/08
