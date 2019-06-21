# 渲染插屏广告

本篇介绍如何使用createFlow进行插屏广告的渲染。

### **实机兼容性**

* 以下为通过实机测试的引擎以及版本，通常情况下，支持同一大版本下同一引擎的渲染（假设支持版本为1.0.0引擎，1.7.0，1.8.0，1.9.0版本的引擎可能都支持）。
* cocos引擎中，请确保在画布渲染完毕之后调用createFlow

### 支持的引擎

| 引擎 | 版本号 |
| :--- | :--- |
| laya | v2.0.0beta5.1 |
| cocos | v2.1.0 |

### **使用实例**

```java
let flowUI = wx.tmSDK.createFlow({
    positionId: 1260，
});
// 监听插屏广告关闭事件
flowUI.onDestory(function({message}) {
    console.log(message)
});
```

### **onError**

```java
flowUI.onError(function(error) {
    console.error(error);
})
```

### **offError**

```java
let callBack = function(error){ // 假设onError的时候绑定的为该函数
    console.log(error)
};
flowUI.offError(callBack);  // 取消某个监听事件
```



