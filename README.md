# html
some
<h2>样式</h2>
使用range.css统一了html5中input range的表现样式。通过background-size属性修改背景尺寸以动态更新进度。

<h2>结构</h2>
使用的是flex-box弹性盒模型，简单嵌套。通过@media screen来更改需要加载的样式，以提升不同视窗设备的可用性。使用了html5中的audio标签以及api。
<h3></h3>

<h2>脚本</h2>
大多使用JQuery的事件监听方法，通过监听用户的行为或者浏览器的行为来执行任务。

<h3>过程中主要解决的问题</h3>
关于html5中input range属性仍然有许多不一致的地方，如firefox中value值为min值时仍然
不归零的情况，还有IE11浏览器下，flex容器崩溃或者显示‘错误’的问题。还有诸如-webkit-,-moz-之类的厂商私有属性(伪元素)的读取和修改

<h3>主要问题的解决办法</h3>
解决办法是区别对待，先判断出浏览器内核，再为不同内核的浏览器修改相应的代码。由于伪元素并不在DOM树当中，因此并不能通过常规方法修改属性，解决办法是
在style兄弟节点的最后面插入style节点，再用html（）方法修改里面的属性
