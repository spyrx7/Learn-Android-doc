# android Activity 生命周期介绍
> 记录学习 activity 生命周期的基本方法

### onCreate 方法
 表示Activity正在被创建，这是生命周期的第一个方法。在这个方法中，我们可以做一些初始化工作，比如调用setContentView 去加载界面资源，初始化Activity需要的数据等。

### onRestart 方法
 表示 Activity 正在重新启动。 一般情况下，当当前 Activity 从不可见重新变为可见状态， onRestart 就会被调用。 这种情形一般是用户行为导致的，比如用户按Home 键切换到桌面或者用户打开了一个新的Activity ，这时候当前的 Activity 就会暂停，也就是 onPause 和 onStop 被执行了，接着回到这个Activity ，就会出现这种情况。

### onStart 方法
 表示Activity正在被启动，即将开始，这时 Activity 已经可见了，但是还没有出现在前台（还在后台），还无法正常交互。这个时候其实可以理解为 Activity 已经显示出来了，但是我们还看不到。

### onResume 
 表示 Activity 已经可见了，并且出现在前台并开始活动。要注意这个和onStart 的对比，onStart 和 onResume 都表示 Activity 已经可见，但是onStart 的时候 Activity 还在后台，onResume 的时候 Activity 才显示在前台。

### onPause
 表示 Activity 正在停止，正常情况下，紧接着onStop就会被调用。在特殊情况下，如果这个时候快速地再回到当前 Actvity，那么onResume会被调用。当然这个是一种特殊情况，用户操作很难重现这一种场景。此时可以做一些存储数据、停止动画等工作，但是注意不能太耗时，因为这会影响到新的Activity 的显示，onPause 必须先执行完，新的 Activity 的 onResume 才会执行。

### onStop
 表示 Activity 即将停止，可以做一些稍微重量级的回收工作，同样不能太耗时。

### onDestroy
 表示 Activity 即将被销毁，这是 Activity 生命周期的最后一个回调，在这里  我们可以做一些回收工作和最终的资源释放。

 这里给了一张图，提供理解。

![](https://developer.android.google.cn/guide/components/images/activity_lifecycle.png?hl=zh-cn)

> 问题1 当启动一个Activity时，会执行什么生命周期方法？

启动一个Activity ，会先执行onCreate 方法 然后执行onStart 方法，再执行 onResume 方法


