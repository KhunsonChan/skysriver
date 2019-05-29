# 为你的游戏接入SDK

### **下载SDK**

在天幕项目中，可以下载当前游戏的SDK，请点击[此处](https://skysriver.gitbook.io/skysriver/kai-shi-shi-yong/zuo-wei-liu-liang-zhu-jie-shou-guang-gao-ding-dan/jie-ru-tian-mu-sdk)参阅如何下载并接入SDK

### **接入SDK**

将下载的sdk文件放置到小游戏工程中，在小游戏game.js中引入SDK

### **注意事项**

小游戏引入SDK时必须遵守如下事项：

* SDK必须放在主包中加载，切勿分包加载
* 在laya引擎中，文件名必须为.min.js结尾，否则会导致编译报错

### **检查接入状态**

可以以此说明来检查引入SDK是否成功。

### **白名单**

使用SDK进行登录时，微信开发者工具控制台无以下类似的错误提示： ![](https://cdn.nlark.com/yuque/0/2019/png/254569/1557225133196-e89b856c-4d1a-4847-9b86-52b7a9350b2e.png)

解决办法： 在微信MP后台配置[域名白名单](https://www.yuque.com/eqrk37/gk0pcl/dg7c7s)

### **登录**

SDK自动静默登录后，微信开发者工具控制台无以下类似的错误提示：

![](https://cdn.nlark.com/yuque/0/2019/png/254569/1557225133185-0e795b92-c3a0-42d1-9ea5-c50699052b96.png)

解决方法： 下载的SDK与当前应用不一致，请到对应的天幕项目下，下载正确的SDK

