# use-strict
严格模式

1. 变量
    * 不允许创建没有var声明的全局变量。
    * 不能对变量调用 delete 操作符。非严格模式允许这样操作，但会静默失败（返回 false）。而在严格模式下，删除变量也会导致错误。
2. 严格模式下对变量名和函数名也有限制。特别地，不能使用 implements、interface、let、package、private、protected、public、static 和 yield 作为变量名。这些都是保留字，将来的 ECMAScript版本中可能会用到它们。
3. 对象
    * 为只读属性赋值会抛出 TypeError；
    * 对不可配置的（nonconfigurable）的属性使用 delete 操作符会抛出 TypeError；
    * 为不可扩展的（nonextensible）的对象添加属性会抛出 TypeError。
4. 函数
    * 严格模式要求命名函数的参数必须唯一。在非严格模式下，这个函数声明不会抛出错误。通过参数名只能访问重名最后一个参数，要访问之前的参数必须通过 arguments 对象。
    * 在非严格模式下，修改命名参数的值也会反映到 arguments 对象中，而严格模式下这两个值是完全独立的。
    * 淘汰了 arguments.callee 和 arguments.caller。在非严格模式下，这两个属性一个引用函数本身，一个引用调用函数。
    * 只能在脚本的顶级和在函数内部声明函数。也就是说，在 if 语句中声明函数会导致语法错误，在非严格模式下可以运行
5. 严格模式已经明确禁止使用 eval 和 arguments 作为标识符，也不允许读写它们的值。意味着以下几种使用方式都会抛出语法错误：
    * 使用 var 声明；
    * 赋予另一个值；
    * 尝试修改包含的值，如使用++；
    * 用作函数名；
    * 用作命名的函数参数；
    * 在 try-catch 语句中用作例外名。
6. 不能使用with
7. 抑制this，在非严格模式下使用函数的 apply()或 call()方法时，null 或 undefined 值会被转换为全局对象。而在严格模式下，函数的 this 值始终是指定的值(null 或 undefined等)，无论指定的是什么值。
8. 去掉了 JavaScript 中的八进制字面量。以 0 开头的八进制字面量过去经常会导致很多错误。
9. parseInt()，八进制字面量在严格模式下会被当作以 0 开头的十进制字面量。
