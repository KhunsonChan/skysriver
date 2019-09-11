# 初始化SDK

{% hint style="info" %}
该接口用于初始化SDK，可配置当前应用的版本号等，某些接口必须初始化SDK之后才能使用
{% endhint %}

## **关联接口**

* [onShareAppMessage](sharing/onshareappmessage.md)
* [shareAppMessage](sharing/shareappmessage.md)
* [createFlow](../../selling/dev-guide/componentization/createflow/)
* [checkFlowIsOpen](../../selling/dev-guide/ad-position-status.md)
* [getFlowConfig](../../selling/dev-guide/api/get-ad-position-config.md)
* [getJudgeConfig](function-switch.md)

## **调用方法**

调用[.init](../../selling/dev-guide/initialization.md)方法实现，示例如下

```javascript
wx.tmSDK.init({
     hideRequestLog: false,
     appVersion: '1.0.0'
});
```

## **传入参数**

| 字段 | 字段类型 | 说明 |
| :--- | :--- | :--- |
| hideRequestLog | boolean | 是否隐藏请求日志 |
| appVersion | string | 当前应用提交微信审核的版本号 |

