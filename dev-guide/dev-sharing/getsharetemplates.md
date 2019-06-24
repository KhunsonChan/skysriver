# getShareTemplates



**前置条件**

使用该接口前，必须先使用[init](https://www.skysriver.com/tianmu_sdk/api/sdk_init.html)方法初始化SDK

**\#调用方法**

```javascript
wx.tmSDK.getShareTemplates().then((res) => {
    console.log(res);
})
```

## **返回值样列**

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

