# 接入天幕SDK

所有需要在天幕接单的流量主游戏，均须接入天幕SDK，只有接入了天幕SDK后，才可实现以下重要的功能。

* [在游戏中创建广告位](create-ad-position.md)
* 接收广告创意
* 统计曝光，点击等数据
* 统计计费数据
* [管理转发素材](../../features/configuration-service/sharing-management.md)
* [功能开关](../../features/configuration-service/switch.md)
* [米大师支付](../../features/configuration-service/mi-da-shi-payment.md)
* [渠道配置管理](../../features/configuration-service/channel-management.md)

因此，请务必接入天幕的SDK，下面将说明如何获取与接入SDK

请在主体中，找到需要接入SDK的游戏，点击游戏名称，进入游戏详情页面开始SDK的接入流程。

以下内容会涉及到技术人员方面的工作，若为运营人员，简单了解即可，在SDK接入完成后，可开始执行[广告位创建工作。](create-ad-position.md)

![](https://cdn.nlark.com/yuque/0/2019/png/254569/1557215260667-68f2f25d-bbc3-4584-99c4-00537d035698.png?x-oss-process=image/resize,w_2000)

![](https://cdn.nlark.com/yuque/0/2019/png/254569/1557215311628-028cef03-467e-40de-9d7a-e489ead36e08.png?x-oss-process=image/resize,w_2000)

### **1. 配置域名白名单**

接入天幕时，您需要在微信小程序后台的域名白名单中添加天幕的域名。

![](https://cdn.nlark.com/yuque/0/2019/png/254569/1557215080025-61922114-f312-45cb-96e0-3633f3593f6c.png)

#### **request**

* https://api.skysriver.com
* https://api.kuaiyugo.com
* https://cdn.kuaiyugo.com
* https://h5game-log.kuaiyugo.com
* https://api.51sfske.com（选填）
* https://api.51staryule.com（选填）
* https://api.51yxstar.com（选填）

#### **upload**

* https://cdn.kuaiyugo.com

#### **download**

* https://cdn.kuaiyugo.com

### **2. 下载SDK**

点击下载，并按下方的说明在小游戏客户端中进行植入。

![](https://cdn.nlark.com/yuque/0/2019/png/254569/1557215353478-29f47126-2525-4910-800b-61eb5606668d.png?x-oss-process=image/resize,w_2000)

### **3. 校验SDK**

接入SDK完成后，请按页面上的要求，进行校验，校验通过后，SDK即接入成功。

![](https://cdn.nlark.com/yuque/0/2019/png/254569/1557215697929-34c9e611-57d1-4050-8665-ba91bad3bb99.png)

SDK接入完成后，可进行广告位的接入，请参阅以下文章，将会阐述如何在游戏中创建广告位，请注意，仅适合开发人员阅读，若您不是开发人员，想了解相关的内容，请与开发人员进行沟通。

{% page-ref page="../../dev-guide/create-ad-position/" %}

 

