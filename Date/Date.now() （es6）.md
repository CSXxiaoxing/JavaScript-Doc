## Date.now() （es6）
**获取当前时间的时间戳**


|             写法              | 参数 |
| :---------------------------: | :--: |
| **let** timestamp = Date.now() |  无  |

> Demo：

```
 let timestamp = Date.now()
 // 1578048973104
```



> 描述:

**now()**  方法返回自 1970年1月1日 00:00:00 UTC 到当前时间的毫秒数，类型为Number。
因为 now() 是Date的一个静态函数，所以必须以 Date.now() 的形式来使用。



> 兼容旧环境:

该方法在 ECMA-262 第五版中被标准化，可以通过下面的代码来兼容那些不支持该方法的引擎。

```
if (!Date.now) {
  Date.now = function now() {
    return new Date().getTime();
  };
}
```

