### vue 滑动的方式：

1. scrollIntoView() 方法可以自动回到上次浏览的位置。

2. 使用window.scrollTo()，该方法需要使用定时器多次调用才能实现滑动效果。

3. 使用vuerouter的scrollBehavior 方法，该方法需要在路由切换时才会触发。