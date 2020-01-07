### filter快速过滤数组元素

```
var arr = [1, 2, 3, 4, 5, 4, 8, 4];
arr = arr.filter(item => item != 4);
console.log(arr);    // 数组去除为4的元素
(5) [1, 2, 3, 5, 8]
```

