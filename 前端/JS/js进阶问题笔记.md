1、var 没有块作用域，let 和 const 有;
声明变量都会提升，但是 var 会被初始化为 undefined，let 和 const 不会初始化;
在块里面可以重新定义变量，如果同样是 let、var 或者未定义，则为同一个变量，如果定义方式 let、var 不一样，则为不同的变量。

2、static 静态方法应该由 class 使用，实例不能使用

3、给原型添加属性：Person.prototype.getFullName

4、构造函数未使用 new，生成值为 undefined

5、js 事件机制

6、js 类型可分为基本类型和对象（有原型），对象是引用传递，对象内的值是值传递，基本类型是值传递，数组也是对象。

7、比较对象应该看引用，{ age: 18 } === { age: 18 }为 false

8、当字符串化一个对象时，它会变成 "[object Object]",所以 a[对象 1]和 a[对象 2]是一样的

9、return 相当于 return undefined

10、引入的模块是 只读 的: 你不能修改引入的模块。只有导出他们的模块才能修改其值。

11、[y] = [1, 2, 3, 4, 5];y 等于 1

12、import 命令是编译阶段执行的,使用 require()，您可以在运行代码时根据需要加载依赖项

13、常规函数是一个带有 constructor 属性的对象（原型对象），箭头函数没有这个 prototype 属性

14、symbol 类型、promise、解构赋值、箭头函数、迭代器

15、有两种访问对象属性的方法：括号表示法或点表示法。点语法会使用该确切名称在对象上查找属性；括号语法会找整个括号内的表达式，具体看 106 题。

16、函数会先在自身寻找变量，有则使用，没有再到外部去寻找。具体看 111 题

17、具体看 116 题

18、对象里找不到某属性，返回 undefined;运行对象里没有的方法，类型错误；运行没定义的方法，引用错误。

19、关于对象内的值：赋值给某变量时，是值传递；调用方法当参数传时，是引用传递；直接解构赋值改对象内属性时，是引用传递。
