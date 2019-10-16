---
description: API接入说明，建议详细阅读
---

# API方式接入广告位

## 接入方式说明

目前天幕广告位接入的方式有两种：

1. 组件化的方式接入（仅支持cocos、laya引擎）
2. api的方式接入

| 广告位类型 | 组件化接入 | **API接入** |
| :--- | :--- | :--- |
| 多Icon广告位 | 支持 | 支持 |
| 浮动窗广告位 | 支持 | 支持 |
| 插屏广告位 | 支持 | 不支持 |
| 伪视频广告位 | 支持 | 不支持 |
| Banner广告位 | 不支持 | 支持 |

{% hint style="warning" %}
我们建议优先使用[组件化的方式](../componentization/)接入广告位：

1. 若你的游戏引擎非cocos，laya
2. 或是组件的样式不满足需求（此情况常见于多Icon广告位）

SDK组件无法满足，则可通过API的方式接入。
{% endhint %}

通过API接入，请参照本篇下方的内容完成接入。

{% hint style="info" %}
接入广告位时，所需要的广告位ID（positionID），请在“[卖量助手-流量主游戏管理](../../main-features/flower-game-manage.md#guang-gao-wei-guan-li)”中获取。
{% endhint %}

涉及到的接口：

* 获取广告位开关：[checkFlowIsOpen](../ad-position-status.md)
* 创意配置获取：[getFlowConfig](get-ad-position-config.md)
* 点击跳转：[flowNavigate](https://doc.skysriver.com/dev-guide/create-ad-position/landing)

## 获取广告位开关状态

需要获取广告位的开启状态，请参阅以下接口：

{% page-ref page="../ad-position-status.md" %}

## **【重要】接口调用**

当游戏中需要展示创意的时候：

1. 首先通过调用[`checkFlowIsOpen`](../ad-position-status.md)，传入广告位ID，获取广告位开关状态：开启/关闭。
2. 如果广告位为开启状态，调用[`getFlowConfig`](get-ad-position-config.md)，传入广告位ID，获取配置。

{% hint style="danger" %}
注意：

每次调用[`getFlowConfig`](get-ad-position-config.md)，对应广告位都会视作**产生曝光**，所以为了数据准确性：

1. 请先获取广告位的开关状态，广告位开启时再调用[`getFlowConfig`](get-ad-position-config.md)\`\`
2. **只有**在每次需要展示创意的时候才调用该接口，不要**提前加载**或**复用上一次的接口返回值**
{% endhint %}

## 浮动窗广告位接入

### **1、type=1** 

若[`getFlowConfig`](get-ad-position-config.md)返回值中type为1时，`positionId`对应的广告位类型是浮动窗类型中的静态图，图片尺寸为：190\*270  
 ![](https://uploader.shimo.im/f/nQvWLNArkEMNVUDJ.png!thumbnail)  
如果创意列表creatives的show\_config中，只有image，则只需渲染该静态图。  


![&#x6D6E;&#x52A8;&#x7A97;&#x5E7F;&#x544A;&#x6548;&#x679C;](../../../.gitbook/assets/image%20%2856%29.png)

### **2、若返回值中存在fps**

如果创意列表`creatives`中有fps，那么对应的广告类型是浮动窗的多帧动图，返回的多个图片素材则需渲染为动态图片，按照fps的值进行**图片轮播**：

> 示例：fps=5，意味着每秒播放5张图片，即0.2秒切换一张

该广告创意实现的效果类似GIF。

### **3、数据刷新规则及点击跳转**

请按照如下说明完成接入：

数据刷新规则请参照：[数据刷新规则](./#shu-ju-shua-xin-gui-ze)

点击后跳转请参照：[点击后跳转](./#dian-ji-hou-tiao-zhuan)

## **多Icon**广告位接入

### **1、type=7**

若[`getFlowConfig`](get-ad-position-config.md)返回值中type为7时，`positionId`对应的是多Icon广告位类型，图片尺寸为：200\*200，请注意，多Icon广告位拥有多个创意，需要全部渲染处理。

{% hint style="danger" %}
这里有个**非常非常非常重要**的注意事项需要说明：

接口返回的创意数组中的内容，是根据**预估收益从高到底进行排序**，请将**排序靠前的创意**展示在**游戏中点击率高**（开发者根据游戏实际情况确定）的位置，以获取最大收益。

因影响广告位的展示效率，接入时建议与游戏策划人员进行沟通，相关链接：[天幕创意下发策略](../../creative-strategy.md)
{% endhint %}

![&#x731C;&#x4F60;&#x559C;&#x6B22;&#x5E7F;&#x544A;&#x6548;&#x679C;](../../../.gitbook/assets/image%20%28147%29.png)

### **2、数据刷新规则及点击跳转**

请按照如下说明完成接入：

数据刷新规则请参照：[数据刷新规则](./#shu-ju-shua-xin-gui-ze)

点击后跳转请参照：[点击后跳转](./#dian-ji-hou-tiao-zhuan)

## Banner广告位接入

### 1、type=11

若[`getFlowConfig`](get-ad-position-config.md)返回值中type为11时，`positionId`对应的是多Icon广告位类型，图片尺寸为：960\*334

### **2、数据刷新规则及点击跳转**

数据刷新规则请参照：[数据刷新规则](./#shu-ju-shua-xin-gui-ze)

点击后跳转请参照：[点击后跳转](./#dian-ji-hou-tiao-zhuan)

## **数据刷新规则**

### **1、自动刷新**

根据`auto_change`的值，自动刷新广告内容；

#### **实现方法**

每次调用[`getFlowConfig`](get-ad-position-config.md)，根据`auto_change`的返回值，设置一个Timer，调用[`getFlowConfig`](get-ad-position-config.md)，展示接口返回的广告配置。

#### **自测方法**

观察游戏中的广告，是否按照接口的返回值自动切换，可通过观察广告图片上的文字内容得知是否切换了广告。

### **2、点击刷新**

根据在上述自动刷新说明的`auto_change`返回值设定的时间内，点击广告，自动刷新广告内容。

**实现方法**

1. 点击后调用[`flowNavigate`](landing.md)，展示接口返回的创意配置。
2. 执行了此刷新后，自动刷新中的timer重新计时。

#### **自测方法**

点击游戏中的广告，可通过观察广告图片上的文字内容得知是否切换了广告。

## **点击后跳转**

点击后跳转的功能由SDK实现，开发者只需调用SDK中的[`flowNavigate`](landing.md)接口，传入对应的广告位ID和创意ID即可。

### **1、**广告位ID获取

在天幕-流量主后台的广告位管理页面，可找到对应广告位ID。

![](../../../.gitbook/assets/image%20%284%29.png)

### 2、创意ID的获取

在调用了[`getFlowConfig`](get-ad-position-config.md)后，返回的`creativeId`的值即为创意ID。

### **3、.flowNavigate**

{% hint style="info" %}
此功能的使用前提：调用了获取广告推广配置的[`getFlowConfig`](get-ad-position-config.md)；
{% endhint %}

[`flowNavigate`](landing.md)接口是用于在用户点击了广告位上的创意后，实现跳转到该创意指定的落地页功能。

> 例如，用户在a游戏某广告位上点击了推广b产品的创意，那么在用户点击后，可以跳转至b产品，这个跳转需要通过[`flowNavigate`](landing.md)接口来实现。

{% hint style="info" %}
注意：

请提前将需要跳转的appid添加只game.json配置列表中，若对此不了解请参阅[微信小程序跳转的规则文档](https://developers.weixin.qq.com/miniprogram/dev/api/open-api/miniprogram-navigate/wx.navigateToMiniProgram.html)，否则会导致跳转不成功
{% endhint %}

