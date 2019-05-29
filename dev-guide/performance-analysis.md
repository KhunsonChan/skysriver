# 性能分析

接入小游戏加载时长后，可以记录用户停留在加载界面的时长。

具体的实现方式可通过`sendLoadingLog` 方法实现，该方法可用于记录游戏进度条加载时长，便于统计与后续优化。

### **调用方法**

调用 `sendLoadingLog` 方法传入类型：

* `progressStart` 用于进度条开始加载
* `progressEnd` 用于进度条结束加载

### **示例**

```java
//进度条开始加载前
wx.tmSDK.sendLoadingLog('progressStart');
...
//进度条加载完成后
wx.tmSDK.sendLoadingLog('progressEnd');
```



