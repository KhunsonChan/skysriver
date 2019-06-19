# .onShareAppMessage

本篇为技术说明文档，具体业务详情，请参阅[转发素材配置](../../features/configuration-service/sharing-management.md)**，**使用前，请[初始化SDK](https://skysriver.gitbook.io/skysriver/ji-shu-zhi-nan/chu-shi-hua-ni-de-sdk)。

此方式适用于用户点击右上角菜单的转发按钮，传入参数与 [`wx.onShareAppMessage`](https://developers.weixin.qq.com/minigame/dev/api/wx.onShareAppMessage.html?search-key=wx.onShareAppMessage) 基本一致，额外增加天幕sdk中 [`getShareTemplates`](http://docs.kuaiyugo.com/sdkdoc2/api/dev_share_getsharetemplates.html) 方法获取的 `channelCode`字段。

**\#**

## **调用方法**

```javascript
wx.tmSDK.onShareAppMessage(function() {
    return {
        scene: 'scene1',
        success: function() {},
        cancel: function() {},
        query: 'a=b&c=d', // 自行定义传入分享的参数, 可在卡片打开后获取到自己的参数
    }
});
```

## **callback函数返回的对象说明**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| scene | string | 传入和天幕后台配置对应场景值 |
| query | string | 自定义分享卡片参数, 可在卡片打开后启动参数中获取到对应的 |
| cancel | Function | 微信分享取消时触发的回调 |
| success | Function | 微信分享成功后触发的回调 |

## **分享成功后回调参数详解**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| shareEventId | String | 本次分享卡片的唯一id |
| errMsg | String | 本次分享的回调信息 |

