# 自定义事件 （.sendEvent）

## 概述

本篇为自定义事件的开发说明，功能说明请参阅：[自定义事件-功能说明](../main-features/diy-event.md)

主要实现逻辑为：在需要埋点上报的事件触发后，利用SDK接口上报事件ID、及事件中参数的具体值；天幕会根据事件ID统计事件触发次数，及事件下不同参数值的触发次数。

## 接入方式

使用SDK的`sendEvent` 记录并上报自定义事件

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

