# 自定义事件 （.sendEvent）

## 概述

`sendEvent` 用于记录并上报自定义事件

{% hint style="info" %}
对于使用自定义事件的场景与触发条件，请与产品人员沟通
{% endhint %}

## **调用方法**

```java
//事件触发
wx.tmSDK.sendEvent('clickStartButton', {
});
//事件触发
wx.tmSDK.sendEvent('buyStuff', { 
    brand: 'CASIO',
    productName: '计算器'
});
```

{% hint style="info" %}
事件部分代码请在后台“天幕——游戏配置——自定义事件”中复制，开发者仅需填充事件中参数的值。
{% endhint %}

{% hint style="info" %}
简单的事件可以不包含参数。
{% endhint %}

