**彻底理解js中this的指向，不必硬背。**

*https://www.cnblogs.com/pssp/p/5216085.html*



**this 指向详细解析（箭头函数）**

*http://www.cnblogs.com/dongcanliang/p/7054176.html*



ES6箭头函数：

箭头函数表达式的语法比函数表达式更短，写法为：(参数1，参数2)=>{函数体}，否则就得这么写function(参数1，参数2){函数体}

并且没有自己的this，arguments，super或new.target。这些函数表达式更适用于那些本来需要匿名函数的地方，并且它们不能用作构造函数。

箭头函数表达式对非方法函数是最合适的，不推荐作为obj的属性使用。

那么在箭头函数中写this.会指向谁？mozilla的解释是：箭头函数不会创建自己的this,它只会从自己的作用域链的上一层继承this

以下两个例子可以体会下，其中第一种是不推荐用的。

示例①：以下代码会输出33,11而不是33,22（obj对象处于全局作用域，因此say2从obj的作用域穿透到全局，打印11）

    var x = 11;
    var obj = {
      x: 22,
      methods: {
        x: 33,
        say: function () { console.log(this.x) },
        say2: () => { console.log(this.x) }
      }
    }
     
    obj.methods.say();
    obj.methods.say2();
示例②：以下代码会输出1，而不是100 

    var age = 99;
     
    function PersonX() {
      this.age = 0;
      setTimeout(() => {
        this.age++;
        console.log(age)
      }, 1000);
    }
     
    PersonX();