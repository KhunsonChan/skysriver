# 渲染伪视频广告

本篇介绍如何使用createFlow进行伪视频广告的渲染。

### **实机兼容性**

* 以下为通过实机测试的引擎以及版本，通常情况下，支持同一大版本下同一引擎的渲染（假设支持版本为1.0.0引擎，1.7.0，1.8.0，1.9.0版本的引擎可能都支持）。
* cocos引擎中，请确保在画布渲染完毕之后调用createFlow
* 实测1.9.3cocos引擎暂不支持该UI渲染

### 支持的引擎

| 引擎 | 版本号 |
| :--- | :--- |
| laya | v1.7.1 |
| laya | v2.0.0beta5.1 |
| cocos | v2.1.0 |

### **使用实例**

```javascript
let flowUI = wx.tmSDK.createFlow({ // 调用createTiger时，立即显示视频广告
    positionId: 1260 // 传入伪视频id
});
```

#### **onClose**

```javascript
flowUI.onClose(res => {
    if (res && res.isEnded) {
      // 正常播放结束，可以下发游戏奖励
    }
})
```

#### offClose

```javascript
let callBack = (error) => { // 假设onError的时候绑定的为该函数
    console.log(error)
};
flowUI.offClose(callBack); // 取消某个监听事件
```

#### **onError**

```javascript
flowUI.onError(function(error) {
    console.error(error);
})
```

#### **offError**

```javascript
let callBack = function(error){ // 假设onError的时候绑定的为该函数
    console.log(error)
};
flowUI.offError(callBack);  // 取消某个监听事件
```

### **监听广告位跳转事件**

```javascript
flowUI.onNavigate(function(error) {
    console.error(error);
})
```

### **取消监听广告位跳转事件**

```javascript
let callBack = function(error){
    console.log(error)
};
flowUI.offNavigate(callBack);  // 取消某个监听事件
```

