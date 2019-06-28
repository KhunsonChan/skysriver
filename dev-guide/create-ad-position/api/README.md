# API方式接入广告位

{% hint style="warning" %}
目前，天幕广告位接入的方式有两种：  
1、组件化的方式接入（仅支持cocos、laya引擎）  
2、api方式接入；
{% endhint %}

我们建议使用[组件化的方式接入广告位](../zhu-jian-hua/)，若你的游戏引擎非cocos，laya，或是有其他特殊的需求，SDK组件无法满足，则可通过API的方式接入。

下面将会针对API的接入的方式进行详细说明。

涉及到的接口：

* [getFlowConfig](get-ad-position-config.md)
* [flowNavigate](https://doc.skysriver.com/dev-guide/create-ad-position/landing)

## **显示规则**

当你需要在游戏中展示广告的时候，可以通过调用SDK的getFlowConfig接口，传入广告位ID，获取广告位的配置。  
注意：在调用SDK的getFlowConfig接口前，请先[初始化](https://doc.skysriver.com/dev-guide/init)。  


## 返回值注意事项

当你调用了getFlowConfig，有几个返回值是需要特别注意的，要根据这些值来确定广告位的类型，并根据不同类型的广告位采用对应的处理方式。

###  **type=1** 

若返回值type为1时，positionId对应的广告位类型是浮动窗类型中的静态图，图片尺寸为：190\*270  
 ![](https://uploader.shimo.im/f/nQvWLNArkEMNVUDJ.png!thumbnail)  
如果创意列表creatives的show\_config中，只有image，则只需渲染该静态图。  
  
 

![&#x6D6E;&#x52A8;&#x7A97;&#x5E7F;&#x544A;&#x6548;&#x679C;](../../../.gitbook/assets/image%20%2827%29.png)

### **若返回值中存在fps**

如果创意列表creatives中有fps，那么对应的广告类型是浮动窗的多帧动图，返回的多个图片素材则需渲染为动态图片，按照fps的值进行图片轮播。

该广告创意实现的效果类似GIF。

### **type=7**

type为7时，positionId对应的是猜你喜欢类型，图片尺寸为：200\*200，请注意，猜你喜欢拥有多个创意，需要全部渲染处理。

这里有个非常重要的注意事项需要说明：

> 接口返回的创意数组，是根据预估收益从高到底进行排序，请将排序靠前的创意展示在游戏中点击率高（开发者根据游戏实际情况确定）的位置，以获取最大收益。

为了能使猜你喜欢广告展示效率达到最高，请按上述说明的需求对展示的猜你喜欢创意进行排序，位置需根据游戏实际情况确定，若未能确定或无特殊需求，可使用我们返回的创意顺序展示即可。

![&#x731C;&#x4F60;&#x559C;&#x6B22;&#x5E7F;&#x544A;&#x6548;&#x679C;](../../../.gitbook/assets/image%20%2861%29.png)

## **数据刷新规则**

### **自动刷新**

根据auto\_change的返回值，自动刷新广告内容；

#### **实现方法**

每次调用getFlowConfig，根据auto\_change的返回值，设置一个Timer，调用getFlowConfig，展示接口返回的广告配置。

#### **自测方法**

观察游戏中的广告，是否按照接口的返回值自动切换，可通过观察广告图片上的文字内容得知是否切换了广告。

### **点击刷新**

根据在上述自动刷新说明的auto\_change返回值设定的时间内，点击广告，自动刷新广告内容。

**实现方法**

1. 点击后调用flowNavigate，使用flowNavigate接口的返回值，展示接口返回的广告配置。
2. 执行了此刷新后，自动刷新中的timer重新计时。

#### **自测方法**

点击游戏中的广告，可通过观察广告图片上的文字内容得知是否切换了广告。

### **点击后跳转**

点击后跳转的功能由SDK实现，开发者只需调用SDK中的flowNavigate接口，传入对应的广告位ID和创意ID即可。

#### 广告位ID获取

在天幕-流量主后台的广告位管理页面，可找到对应广告位ID。

![](../../../.gitbook/assets/image%20%283%29.png)

#### 创意ID的获取

在调用了getFlowConfig后，返回的creativeId的值即为创意ID。

### **flowNavigate**

{% hint style="info" %}
此功能的使用前提：调用了获取广告推广配置的[getFlowConfig](get-ad-position-config.md)；
{% endhint %}

这个接口是用于在用户点击了广告位上的创意后，实现跳转到该创意指定的落地页功能。

例如，用户在a游戏某广告位上点击了推广b产品的创意，那么在用户点击后，可以跳转至b产品，这个跳转需要通过[flowNavigate](landing.md)接口来实现。

这里需要注意：请提前将需要跳转的appid添加只game.json配置列表中，若对此不了解请参阅[微信小程序跳转的规则文档](https://developers.weixin.qq.com/miniprogram/dev/api/open-api/miniprogram-navigate/wx.navigateToMiniProgram.html)，否则会导致跳转不成功

## 广告位开启状态

需要获取广告位的开启状态，请参阅以下接口：

{% page-ref page="../zhu-jian-hua/get-ad-position-status.md" %}

