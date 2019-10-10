---
description: 本篇介绍如何使用createFlow进行浮动窗广告的渲染。
---

# 渲染浮动窗广告位

## **实机兼容性**

* 以下为通过实机测试的引擎以及版本，通常情况下，支持同一大版本下同一引擎的渲染（假设支持版本为1.0.0引擎，1.7.0，1.8.0，1.9.0版本的引擎可能都支持）。
* cocos引擎中，请在画布初始化完毕后才调用createFlow

## 支持的引擎

| 引擎 | 版本号 |
| :--- | :--- |
| laya | v1.7.1 |
| laya | v2.0.0beta5.1 |
| cocos | v1.9.3 |
| cocos | v2.0.5 |

## **使用实例**

```java
let flowUI = wx.tmSDK.createFlow({
    positionId: 1260，
    width: 200, // 可设置浮动 icon 尺寸
    x: 0,     
    y: 300,  
});
// 监听错误事件
flowUI.onError(function({message}){
    console.log(message)
});
```

## **销毁**

正常情况下，游戏场景切换时，该UI组件会自动销毁。如果需要在某些场景销毁该组件，请使用destroy方法。

```java
flowUI.destroy();
```

## **可选参数: width**

1. 浮动窗类型下，可等比例设置渲染宽度，最小值为100，比例固定为190:270。
2. 设置的宽度类型会根据当前尺寸画布与1080\*1920的标准尺寸画布进行缩放。

```java
let flowUI = wx.tmSDK.createFlow({
    ...,  
    width: 250, // 自定义浮动icon宽度为：在1080*1920尺寸下的宽度为250px。
});
```

## **可选参数: zIndex**

1. 可自定义设置渲染组件的层级
2. 闪屏类型默认值则为加999999999 + 1，其他类型默认值为999999999。
3. 实际显示的层级数会被引擎自动调整

```java
let flowUI = wx.tmSDK.createFlow({
    ...,  
    zIndex: 250, // 设置组件层级为250, 实际显示的层级会被引擎所调整。
});
```

## **监听广告位跳转事件**

```javascript
flowUI.onNavigate(function(error) {
    console.error(error);
})
```

## **取消监听广告位跳转事件**

```javascript
let callBack = function(error){
    console.log(error)
};
flowUI.offNavigate(callBack);  // 取消某个监听事件
```

