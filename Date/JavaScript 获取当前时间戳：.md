## JavaScript 获取当前时间戳：

> #### 第一种方法：毫秒数为零

```
let timestamp = Date.parse(new Date());
// 1578116624000
```



> ####  第二种方法：毫秒数不为零

**IE8 以上版本 ( es6 ) **

```
let timestamp = Date.now();
// 1578116863634
```
**IE8 以下版本**

```
if (!Date.now) {
     Date.now = function() { 
     	return new Date().getTime();  // 或 new Date().valueOf()，结果相同。
     };
 }
```



> #### 其他   

**jQuery 获取时间戳**

```
var timestamp = $.now();
```
