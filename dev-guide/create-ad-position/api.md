# 广告位API方式接入

{% hint style="warning" %}
目前，天幕广告位接入的方式有两种：1、组件化的方式接入（仅支持cocos、laya引擎）2、api方式接入。
{% endhint %}

涉及到的接口：

* [getFlowConfig](https://doc.skysriver.com/dev-guide/create-ad-position/get-ad-position-config)
* [flowNavigate](https://doc.skysriver.com/dev-guide/create-ad-position/landing)

### **显示规则**

当需要展示广告的时候，调用SDK的getFlowConfig接口，传入广告位ID。  
注意：在调用SDK的getFlowConfig接口前，请先[初始化](https://doc.skysriver.com/dev-guide/init)。  


###  **type=1** 

type为1时，positionId对应的是浮动窗类型，图片尺寸为：190\*270  
 ![](https://uploader.shimo.im/f/nQvWLNArkEMNVUDJ.png!thumbnail)  
如果创意列表creatives的show\_config中，只有image，则只需渲染该静态图。  
  


### **若返回值中存在fps**

如果创意列表creatives中，有fps，多个图片素材则需渲染为动态图片，按照fps的值进行图片轮播。



### **type=7**

type为7时，positionId对应的是猜你喜欢类型，图片尺寸为：200\*200  
 ![](https://uploader.shimo.im/f/IMQJYgTrvXsRk6p8.png!thumbnail)  
猜你喜欢拥有多个创意，需要全部渲染处理  


### **数据刷新规则**

  
1）**自动刷新**

根据auto\_change的返回值，自动刷新广告内容；

**实现方法**

每次调用getFlowConfig，根据auto\_change的返回值，设置一个Timer，调用getFlowConfig，展示接口返回的广告配置。

**自测方法**

观察游戏中的广告，是否按照接口的返回值自动切换，可通过观察广告图片上的文字内容得知是否切换了广告。

2）**点击刷新**

根据在上述1中的auto\_change返回值设定的时间内，点击广告，自动刷新广告内容。

**实现方法**

a、点击后调用flowNavigate，使用flowNavigate接口的返回值，展示接口返回的广告配置。

b、执行了此刷新后，自动刷新中的timer重新计时。

**自测方法**

点击游戏中的广告，可通过观察广告图片上的文字内容得知是否切换了广告。

### **点击后跳转**

点击后跳转的功能由SDK实现，开发者只需调用SDK中的flowNavigate接口，传入对应的广告位ID和创意ID即可。

创意ID的获取：

在调用了getFlowConfig后，返回的creativeId的值即为创意ID。

### **flowNavigate**

* 用于实现点击推广创意后跳转到落地页的功能；
* 此功能的使用前提：调用了获取广告推广配置getFlowConfig；
* 此接口需将当前需要跳转的appid添加到game.json配置列表中，请参阅[微信小程序跳转的规则文档](https://developers.weixin.qq.com/miniprogram/dev/api/open-api/miniprogram-navigate/wx.navigateToMiniProgram.html)；

