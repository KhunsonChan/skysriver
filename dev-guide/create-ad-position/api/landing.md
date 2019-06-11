# .flowNavigate

{% hint style="warning" %}
使用该接口前，请先进行[SDK初始化](https://skysriver.gitbook.io/skysriver/ji-shu-zhi-nan/chu-shi-hua-ni-de-sdk)
{% endhint %}

该接口用于实现点击推广创意后跳转到落地页的功能，例如

1. 此功能的使用前提：调用了获取广告推广配置[getFlowConfig](https://www.yuque.com/eqrk37/gk0pcl/okpygt)
2. 此接口需将当前需要跳转的appid添加到game.json配置列表中，请参阅[微信小程序跳转的规则文档](https://developers.weixin.qq.com/miniprogram/dev/api/open-api/miniprogram-navigate/wx.navigateToMiniProgram.html)

### **如何配置game.json（小游戏）**

```java
{
  ...
  "navigateToMiniProgramAppIdList": [
    "wxce8556babd23a6b3" //填入跳转游戏的appid
  ]
  ...
}
```

### **使用场景**

1. 在游戏的开始和结算页中添加按钮，点击后调用此方法，自动跳转后台配置的平台。
2. 此接口调用只适用于版本库 2.2.0 以上，所有开发者在调用时注意要把开发工具的版本库调到2.2.0以上的版本，否则会报错。

## **调用方法**

```java
wx.tmSDK.flowNavigate({
    positionId: positionId, // 广告位id, 请先使用该id获取推广创意列表
    creativeId: creativeId,  // 传入获取到的creativeId
}).then((newList)=>{
    console.log('跳转成功')
    console.log('自动刷新列表：', newList)//返回最新列表 
}).catch((error)=>{
    console.log('跳转失败', error);
})
```

\*\*\*\*

## **传入值详解**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| positionId | Number | 当前点击的positionId |
| creativeId | Number | 当前点击的creativeId |

## **返回值**

返回值和[getFlowConfig](https://www.yuque.com/eqrk37/gk0pcl/okpygt)结构一致, 请参考getFlowConfig文档



