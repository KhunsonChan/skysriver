# 渲染猜你喜欢广告

### **实机兼容性**

* 以下为通过实机测试的引擎以及版本，通常情况下，支持同一大版本下同一引擎的渲染（假设支持版本为1.0.0引擎，1.7.0，1.8.0，1.9.0版本的引擎可能都支持）。
* cocos引擎中，请确保在画布渲染完毕之后调用createFlow

| 引擎 | 版本号 |
| :--- | :--- |
| laya | v1.7.1 |
| laya | v2.0.0beta5.1 |
| cocos | v1.9.3 |
| cocos | v2.0.5 |

### **使用实例**

```java
let flowUI = wx.tmSDK.createFlow({
    positionId: 1260，
    width: 375, // 设置尺寸，最小为类似微信banner的300，最大为微信视图宽
    x: 0,     
    y: 300,  
});
// 监听错误事件
flowUI.onError(function({message}) {
    console.log(message)
});
```

### **销毁**

正常情况下，游戏场景切换时，该UI组件会自动销毁。如果需要在某些场景销毁该组件，请使用destroy方法。

```java
flowUI.destroy();
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



