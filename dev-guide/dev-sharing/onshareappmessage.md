# .onShareAppMessage

具体业务详情，请参阅[转发素材管理](https://skysriver.gitbook.io/skysriver/gong-neng-jie-shao/yun-pei-zhi-fu-wu/zhuan-fa-su-cai-guan-li)

使用前，请[初始化SDK](https://skysriver.gitbook.io/skysriver/ji-shu-zhi-nan/chu-shi-hua-ni-de-sdk)。

### **调用方法**

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

### **callback函数返回的对象说明**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| scene | string | 传入和天幕后台配置对应场景值 |
| query | string | 自定义分享卡片参数, 可在卡片打开后启动参数中获取到对应的 |
| cancel | Function | 微信分享取消时触发的回调 |
| success | Function | 微信分享成功后触发的回调 |

### **分享成功后回调参数详解**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| shareEventId | String | 本次分享卡片的唯一id |
| errMsg | String | 本次分享的回调信息 |



