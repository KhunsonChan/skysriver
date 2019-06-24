# .getShareTemplates

本篇为技术说明文档，具体业务详情，请参阅[转发素材配置](../../features/configuration-service/sharing-management.md)**，**使用前，请[初始化SDK](https://skysriver.gitbook.io/skysriver/ji-shu-zhi-nan/chu-shi-hua-ni-de-sdk)。

开发者可通过这个接口接收保存在天幕上的分享素材相关数据，具体返回的数据，请参阅下文中的返回值样例。

### **调用方法**

```javascript
wx.tmSDK.getShareTemplates().then((res) => {
    console.log(res);
})
```

### **返回值样例**

```javascript
{
    "scene_1":[{
        "channel_code": "channelA",         //渠道码
        "title":"分享标题",
        "image":"分享图片",
        "path":"pages/index/index",         //跳转小程序路径
        "scene":"scene_1",                  //使用的场景
    }],
    "scene_2":[{
        "channel_code": "channelB",         //渠道码
        "title":"分享标题",
        "image":"分享图片",
        "path":"pages/index/index",         //跳转小程序路径
        "scene":"scene_2",                  //使用的场景
    }]
}
```

## **返回值详解**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| channel\_code | String | 分享渠道码 |
| title | String | 分享标题 |
| image | String | 分享图片地址 |
| path | String | 跳转小程序路径 |
| scene | String | 场景值 |

