# .shareAppMessage

本篇内容为技术说明文档，具体业务详情，请参阅[转发素材配置](../../features/configuration-service/sharing-management.md)，使用前，请[初始化SDK](https://www.yuque.com/eqrk37/gk0pcl/xbni48)。

此方式用于小游戏主动分享时调用，传入参数与 [`wx.shareAppMessage`](https://developers.weixin.qq.com/minigame/dev/api/wx.shareAppMessage.html?search-key=wx.ShareAppMessage) 基本一致。

## **调用方法**

```javascript
wx.tmSDK.shareAppMessage({
    scene: 'scene1', // 必填，与后台配置对应的场景值
    title: 'xxx' // 可选设置，自定义分享标题，优先级比设置scene中自动设置的title高
    imageUrl: 'xxx' // 可选设置，自定义分享标题，优先级比设置scene中自动设置的imageUrl高
    success: function() {},
    cancel: function() {},
    query: 'a=b&c=d', // 自行定义传入分享的参数
});
```

### **callback函数返回的对象说明**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| scene | string | **必填**, 传入和天幕后台配置对应场景值，如果该场景下有多个素材，将自动随机获取该场景下的素材 |
| query | string | **非必填**，自定义分享卡片参数, 可在卡片打开后启动参数中获取到对应的 |
| title | string | **非必填**，自定义分享的标题，当scene存在时，将覆盖scene对应的素材标题 |
| imageUrl | string | **非必填**，自定义分享的标题，当scene存在时，将覆盖scene对应的素材图片 |
| cancel | Function | 微信分享取消时触发的回调 |
| success | Function | 微信分享成功后触发的回调 |

### **分享成功后回调参数详解**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| shareEventId | String | 本次分享卡片的唯一id |
| errMsg | String | 本次分享的回调信息 |

