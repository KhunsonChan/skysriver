# .getFlowConfig

{% hint style="warning" %}
使用该接口前，请先进行[SDK初始化](https://skysriver.gitbook.io/skysriver/ji-shu-zhi-nan/chu-shi-hua-ni-de-sdk)
{% endhint %}

该接口用于获取广告位id对应配置详情，调用该接口后，请根据接口的返回值，采用对应的方式处理，下方会针对浮动窗广告和猜你喜欢广告位进行说明。

#### 创意ID的获取

调用了getFlowConfig后，返回的creativeId的值即为创意ID

## **调用方法**

```java
wx.tmSDK.getFlowConfig({
     positionId: positionId
}).then((config) => {
    console.log('该广告位当前配置', config);
});
```

## **传入参数**

positionId将对应的不同类型返回值，使用前请确认当前使用的positionId类型

| 字段 | 字段类型 | 说明 |
| :--- | :--- | :--- |
| positionId | string | 广告位id |

## **返回值与广告类型**

### **浮动窗广告**

* type为1时，positionId对应的是浮动窗类型
* 如果创意列表creatives的show\_config中，只有image，则只需渲染该静态图

```java
{
    "isOpen":true,
    "type": 1, // 浮动icon类型
    "auto_change":10,
    "creatives":[
        {
            "creativeId":162,
            "positionId":"1013280",
            "show_config":{
                "image": "https://cdn.kuaiyugo.com/appprogram/tiger/admin/2018-11-06_6fe2c240-e1a7-11e8-bc47-27d9eee1c822.png",
                "show_type":0 // 动态效果
            },
            "size":"190x270" // 广告位尺寸比例
        }
    ]
}
```

* 如果创意列表creatives中，有fps，多个图片素材则需渲染为动态图片，按照1/fps每秒的时间切换每张图片

```java
{
    "isOpen":true,
    "type": 1,
    "auto_change":10,
    "creatives":[
        {
            "creativeId":162,
            "positionId":"1013280",
            "show_config":{
                "fps":0.5,
                "images":["https://cdn.kuaiyugo.com/appprogram/tiger/admin/2018-11-06_6fe2c240-e1a7-11e8-bc47-27d9eee1c822.png","https://cdn.kuaiyugo.com/appprogram/tiger/admin/2018-11-06_7296e5c0-e1a7-11e8-9e7e-c3d1548f6807.png","https://cdn.kuaiyugo.com/appprogram/tiger/admin/2018-11-06_74d033f0-e1a7-11e8-bc47-27d9eee1c822.png","https://cdn.kuaiyugo.com/appprogram/tiger/admin/2018-11-06_76f7a7d0-e1a7-11e8-9e7e-c3d1548f6807.png","https://cdn.kuaiyugo.com/appprogram/tiger/admin/2018-11-06_794679d0-e1a7-11e8-bc47-27d9eee1c822.png","https://cdn.kuaiyugo.com/appprogram/tiger/admin/2018-11-06_7ca4c000-e1a7-11e8-9e7e-c3d1548f6807.png","https://cdn.kuaiyugo.com/appprogram/tiger/admin/2018-11-06_7ebeed70-e1a7-11e8-bc47-27d9eee1c822.png","https://cdn.kuaiyugo.com/appprogram/tiger/admin/2018-11-06_80b650a0-e1a7-11e8-9e7e-c3d1548f6807.png","https://cdn.kuaiyugo.com/appprogram/tiger/admin/2018-11-06_8b929e70-e1a7-11e8-bc47-27d9eee1c822.png","https://cdn.kuaiyugo.com/appprogram/tiger/admin/2018-11-06_985deb00-e1a7-11e8-9e7e-c3d1548f6807.png"],
                "show_type":0
            },
            "size":"190x270"
        }
    ]
}
```

#### \*\*\*\*

### **猜你喜欢**

* type为7时，positionId对应的是猜你喜欢类型
* 猜你喜欢拥有多个创意，需要全部渲染处理

```java
{
    "isOpen":true,
    "type": 1, // 浮动icon类型
    "auto_change":10,
    "creatives":[
        {
            "creativeId":162,
            "positionId":"1013280",
            "show_config":{
                "image": "https://cdn.kuaiyugo.com/appprogram/tiger/admin/2018-11-06_6fe2c240-e1a7-11e8-bc47-27d9eee1c822.png",
                "title": '游戏名' //游戏名称 
            },
        },
         {
            "creativeId":162,
            "positionId":"1013280",
            "show_config":{
                "image": "https://cdn.kuaiyugo.com/appprogram/tiger/admin/2018-11-06_6fe2c240-e1a7-11e8-bc47-27d9eee1c822.png",
                "title": '游戏名' //游戏名称 
            },
        }
    ]
}
```

#### \*\*\*\*

### **返回参数**

| 字段 | 字段类型 | 说明 |
| :--- | :--- | :--- |
| isOpen | boolean | 广告位是否开启 |
| type | string | 该广告位的类型 |
| auto\_change | number | 自动切换时间 |
| creatives | Array | 该广告位可渲染的创意列表, 浮动icon类型该数组有且只有一个 |
| creativeId | string | 创意id |
| positionId | string | 广告位id |
| show\_config | object | 广告位素材详情 |
| show\_config.title | string | 素材对应渲染的标题 |
| show\_config.image | string | 素材图片 |
| title | string | 猜你喜欢的广告文案 |

