# 初始化你的SDK

{% hint style="info" %}
该接口用于初始化SDK，可配置当前应用的版本号等，某些接口必须初始化SDK之后才能使用
{% endhint %}

### **关联接口**

* [onShareAppMessage](https://www.yuque.com/eqrk37/gk0pcl/ntp4sq)
* [shareAppMessage](dev-sharing/shareappmessage.md)
* [createFlow](create-ad-position/shi-yong-createflow-ran.md)
* [checkFlowIsOpen](create-ad-position/huo-qu-guang-gao-wei-kai-qi-zhuang-tai.md)
* [getFlowConfig](create-ad-position/huo-qu-guang-gao-wei-id-dui-ying-pei-zhi.md)
* [getJudgeConfig](function-switch.md)

### **调用方法**

调用[.init](chu-shi-hua-ni-de-sdk.md)方法实现，示例如下

```java
wx.tmSDK.init({
     hideRequestLog: false,
     appVersion: '1.0.0'
});
```

### **传入参数**

| 字段 | 字段类型 | 说明 |
| :--- | :--- | :--- |
| hideRequestLog | boolean | 是否隐藏请求日志 |
| appVersion | string | 当前应用提交微信审核的版本号 |

