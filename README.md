### 简要 ###
在这个项目的页面中，用到了JS面向对象的思想、AMD模块编程、jQuery、requireJS、继承、事件监听等前端的知识点。其中一些基础的关于DOM的操作也有不少，包括创建节点，设置class或者CSS样式等一系列的基础运用。这可以算作是这段时间以来前端学习的小结。
### 开发工具 ###
> 工欲善其事必先利其器

1. 最开始是选择eclipse工具，创建项目。中途想要用git管理项目，但是eclipse上的git插件未配置，而且在使用eclipse最开始的时候启动很慢，让人有点蛋疼。所以就选择在本地浏览器预览，使用编辑器书写代码。这里使用了Sublime Text3。由于没有搭建本地web服务，于是又选择了Nginx作为服务容器。

为什么要搭建一个web服务？
这里会提示这样一个错误。

``XMLHttpRequest cannot load file:///****.html. Cross origin requests are only supported for protocol schemes: http, data, chrome, chrome-extension, https, chrome-extension-resource.
text.get @ text.js:325``

浏览器是默认不支持异步模块加载的。至于简单的部分可以不用web服务就可以预览的。不过，还是需要习惯写项目时候配置好项目的基础运行环境。比如基础的web服务器，一般eclipse中是Tomcat容器，属于Apache系列，nginx也可以，不过目前还是Apache为主流。

2. 关于git管理的工具

windows桌面管理工具，只需要登录账号就好了。连push命令都不需要敲了。不过反应速度不是很好的。所以基础的命令还是需要掌握的。

3. 工具毕竟只是工具，选择一个适合自己的工具，可以提高开发效率。个人是比较喜欢Sublme Text.
轻量，配置想要的插件和主题，书写代码感觉还是不错的。

现在前端的开发工具层出不穷，选择合适的工具完成相应的任务。

### 问题总结 ###

1. 对于页面部分逻辑的分析出现一定的失误，不能准确快速地将具体的需求和代码设计紧密联系在一起。有时是需求没有搞清楚，即使这个需求已经是很简单的，但是还是会出现一点偏差。有时就是明确需求，但是代码这块还是有点问题，之前学习的基础的知识点和实际运用还是存在一定的距离。所以第一个问题在于对于这个简单的页面从开始到写代码没有一个比较清晰的思路。实际操作起来磕磕碰碰的，遇到一个问题会卡在那里纠结一段时间。如果没有好的思路，自己动手写代码是没有必要的。除非是运气好碰对了。但是不可能每次运气都会这么好的。

2. 结合这个项目中的一个组件来说。这个组件的功能就是现实七天的日期。这个日期包括月份和几号，还有某一天是星期几。左右还有一个按钮。实现下一个七天或者前面七天的信息的一个跳转。
 简单地思路是：


   
    首先得到一个数组，这个数组包括所有的信息，而且这个数组的长度是七的倍数。否则对这个数组的操作不是很容易的额。在得到这个数组后，就要对这个数组的信息进行分割。然后设置标志，决定按钮点击事件后具体显示哪一部分分割后数组的内容。这个标志初始为零，每次点击事件的执行，自加或者自减。至于渲染页面的元素动态生成，没有什么特别难的地方。还有设置边界不能点击的问题则是通过添加或者移除class。动手写代码还是很快的，效果也完美实现了。可是没有想到的是：后来在做另外一个组件的时候，需要得到之前一个组件的部分数据。可是再看之前写的组件，方法几乎写在一起了。不可能将想要的数据返回给新的组件。确实一个小组件的实现，有各种方式。但是最适合的也就那么一种。事实证明，那个组件不能用了。需要重写。针对一个完整的项目而言，每一个组件的实现不是说当前的一个小的功能实现就好了。如果另外一个组件依赖于前一个组件，前一个组件写的很糟糕的话，就要重新书写，这是很浪费时间和精力的。最后，将这个组件重新写了一下，多了几个方法，但是我能从这个组件得到想到的东西。而且条理也更加清晰了。即使代码比之前是多了一些，这些是值得的。

### 更新 ###
1. 页面在构建之前，可以先以静态页面搭建，也就是说HTML元素将页面所要展示的内容全部固定，再由CSS将页面的表现形式美化。在学习AMD模式中，requirejs中有插件完成将html页面处理动态添加至页面中。这样，如果页面有需求改变内容的时候，那么只需要将模块中数据修改一下就可以了。这样也带来了一定的性能问题。由JavaScript动态渲染页面肯定不会比静态的快。所以再考虑页面某些部分的完成，如果是不需要经常改变的地方，就没有必要用这种方式。技术始终再解决新的问题的道路上，新技术的产生确实能够解决一些问题，但是又会产生新的问题。这就是技术革新的魅力所在了。从解决问题的实际考虑中思考，合理使用技术，解决问题，是非常重要的。
2. CSS不难，写页面的时候才会真正好好学习一番，所以，不断地练习，CSS水平就会提高的，似乎是没有比较好的捷径可走，有点失落。（逃

### 后续 ###

#### 更新一 ####

1. 页面在构建之前，可以先以静态页面搭建，也就是说HTML元素将页面所要展示的内容全部固定，再由CSS将页面的表现形式美化。在学习AMD模式中，requirejs中有插件完成将html页面处理动态添加至页面中。这样，如果页面有需求改变内容的时候，那么只需要将模块中数据修改一下就可以了。这样也带来了一定的性能问题。由JavaScript动态渲染页面肯定不会比静态的快。所以再考虑页面某些部分的完成，如果是不需要经常改变的地方，就没有必要用这种方式。技术始终再解决新的问题的道路上，新技术的产生确实能够解决一些问题，但是又会产生新的问题。这就是技术革新的魅力所在了。从解决问题的实际考虑中思考，合理使用技术，解决问题，是非常重要的。
2. CSS不难，写页面的时候才会真正好好学习一番，所以，不断地练习，CSS水平就会提高的，似乎是没有比较好的捷径可走，有点失落。（逃

#### 更新二 ####

1. img标签属性：onerror="this.src=''",当图片的src资源未能加载，比如图片资源不存在，或者路径写错，可以借助onerror属性完成异常情况的处理。
2. 加载html模板填充数据时，需要考虑数据的长度，否则数据的填充导致页面需要渲染的部分撑出边界。所以数据在填充之前需要根据实际实际情况进行修改。利用slice方法截取数组，或者对数据属性值的判断，设置数据的新属性。

3. readmore和css样式设置文字多出后实现省略号结尾
   - readmore插件 *多行文字*
   - `` .text-ellipsis{
	   overflow:hidden;
	   text-overflow:ellipsis;
	   white-space:nowrap;
	   }``
	*单行文字*
	
	结合实际情况使用。

### 最后 ###

~~这个页面的代码还是存在一定的问题，后续优化更新。。。~~

这次前端小结总共三个页面，彼此应该是相互联系的，但是页面还是不够多，某些逻辑跳转会很突兀的。所以这里不做过多的要求。毕竟做完一套完整的系统，是需要团队合作共同完成的。
