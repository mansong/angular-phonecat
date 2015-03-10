我们还是通过前一个练习来介绍引导AngularJS应用。下面的介绍比较抽象，基本上理解了代码实现方式以及Angular托管了动态更新就行了。

通过ngApp指令来自动引导AngularJS应用是一种简洁的方式，适合大多数情况。在高级开发中，例如使用脚本装载应用，您也可以使用bootstrap手动引导AngularJS应用。

AngularJS应用引导过程有3个重要点：

1. 注入器(injector)将用于创建此应用程序的依赖注入(dependency injection)；
2. 注入器将会创建根作用域作为我们应用模型的范围；
3. AngularJS将会链接根作用域中的DOM，从用ngApp标记的HTML标签开始，逐步处理DOM中指令和绑定。

一旦AngularJS应用引导完毕，它将继续侦听浏览器的HTML触发事件，如鼠标点击事件、按键事件、HTTP传入响应等改变DOM模型的事件。
这类事件一旦发生，AngularJS将会自动检测变化，并作出相应的处理及更新。