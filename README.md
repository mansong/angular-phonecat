**视图和模板**

我们把前面练习中的静态编码的手机列表替换掉了，这里我们使用```ngRepeat```指令和两个用花括号包裹起来的AngularJS表达式
——```{{phone.name}}```和```{{phone.snippet}}```——能达到同样的效果。

1. 在```<li>```标签里面的```ng-repeat="phone in phones"```语句是一个AngularJS迭代器。这个迭代器告诉AngularJS用第一个
```<li>```标签作为模板为列表中的每一部手机创建一个```<li>```元素。

2. 正如我们在第0步时学到的，包裹在```phone.name```和```phone.snippet```周围的花括号标识着数据绑定。和常量计算不同的是，
这里的表达式实际上是我们应用的一个数据模型引用，这些我们在```PhoneListCtrl```控制器里面都设置好了。

**模型和控制器**

在```PhoneListCtrl```控制器里面初始化了数据模型（这里只不过是一个包含了数组的函数，数组中存储的对象是手机数据列表）

尽管控制器看起来并没有起到什么控制的作用，但是它在这里起到了至关重要的作用。通过给定我们数据模型的语境，控制器允许我们建立模型和视图之间的数据绑定。
我们是这样把表现层，数据和逻辑部件联系在一起的：

1. ```PhoneListCtrl```——控制器方法的名字（在JS文件```controllers.js```中）和```<body>```标签里面的ngController指令的值相匹配。
2. 手机的数据此时与注入到我们控制器函数的作用域（```$scope```）相关联。当应用启动之后，会有一个根作用域被创建出来，
而控制器的作用域是根作用域的一个典型后继。这个控制器的作用域对所有```<body ng-controller="PhoneListCtrl">```标记内部的数据绑定有效。

>AngularJS的作用域理论非常重要：一个作用域可以视作模板、模型和控制器协同工作的粘接器。AngularJS使用作用域，同时还有模板中的信息，数据模型和控制器。
这些可以帮助模型和视图分离，但是他们两者确实是同步的！任何对于模型的更改都会即时反映在视图上；任何在视图上的更改都会被立刻体现在模型中。