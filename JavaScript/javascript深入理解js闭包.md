**javascript深入理解js闭包**

*https://www.cnblogs.com/xiangqianjin/articles/6595115.html*



**JS中的闭包问题**

*https://segmentfault.com/q/1010000000495598*

```
var fn = object.getNameFunc(); fn() // The Window // fn 等价于 window.fn ,所以此时的this指的是window // 而 getName 是 object 调用的,this指的是object object.getName(); //My Object   
```

将`getName`内容改成`alert(name);` 又弹出了The Window

因为getName 的作用域中没有name的定义，便像上级作用域寻找（全局作用域 window）即 window.name = 'The Window'

