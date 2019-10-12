# .onShareAppMessage

## 概述

适用于用户点击右上角菜单的转发按钮时调用，传入参数与[`wx.onShareAppMessage`](https://developers.weixin.qq.com/minigame/dev/api/wx.onShareAppMessage.html?search-key=wx.onShareAppMessage) 基本一致。

{% hint style="warning" %}
使用该接口前，请先进行[SDK初始化](../../../selling/dev-guide/initialization.md)
{% endhint %}

## **调用方法**

```javascript
wx.tmSDK.onShareAppMessage(function(){
  return {
       scene: 'scene1', // 必填，分享位ID
       title: 'xxx' // 可选设置，自定义分享标题，优先级比设置scene中自动设置的title高
       imageUrl: 'xxx' // 可选设置，自定义分享标题，优先级比设置scene中自动设置的imageUrl高
       success: function() {},
       cancel: function() {},
       query: 'a=b&c=d', // 自行定义传入分享的参数, 可在卡片打开后获取到自己的参数
    }
});
```

## **callback函数返回的对象说明**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| scene | string | **必填**,，天幕后台配置的分享位ID，如果该分享位下有多个素材，将自动随机获取该分享位下的素材 |
| query | string | **非必填**，自定义分享卡片参数, 可在卡片打开后启动参数中获取到对应的 |
| title | string | **非必填**，自定义分享的标题，当scene存在时，将覆盖scene对应的素材标题 |
| imageUrl | string | **非必填**，自定义分享的标题，当scene存在时，将覆盖scene对应的素材图片 |
| cancel | Function | 微信分享取消时触发的回调 |
| success | Function | 微信分享成功后触发的回调 |

## **分享成功后回调参数详解**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| shareEventId | String | 本次分享卡片的唯一id |
| errMsg | String | 本次分享的回调信息 |

