# android Activity 生命周期介绍
> 记录学习 activity 生命周期的基本方法

onCreate 方法
> 表示Activity正在被创建，这是生命周期的第一个方法。在这个方法中，我们可以做一些初始化工作，比如调用setContentView 去加载界面资源，初始化Activity需要的数据等。

onStart 方法
onResume 
onPause
onStop
onDestroy

> 问题1 当启动一个Activity时，会执行什么生命周期方法？

启动一个Activity ，会先执行onCreate 方法 然后执行onStart 方法，再执行 onResume 方法


