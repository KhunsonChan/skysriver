---
description: 开发者需通过该配置表来控制前端的功能是否开启
---

# 版本控制 （.getJudgeConfig）

## 概述

本篇为版本控制的开发说明，功能说明请参阅：[版本控制-功能说明](../main-features/features-switch.md)

主要实现逻辑为：针对不同版本，SDK返回TRUE（1）/FALSE（0），根据返回值的不同，按约定进行不同的处理（如返回TRUE（1）是展示广告、返回FALSE（0）是关闭广告）。

## **接入方式**

使用SDK的 `getJudgeConfig` 接口来实现。

{% hint style="warning" %}
使用该接口前，请先进行[SDK初始化](../../selling/dev-guide/initialization.md)
{% endhint %}

## **调用方法**

```javascript
wx.tmSDK.getJudgeConfig().then(res=>{  
    console.log(res)  
})
```

## **返回值样例**

```javascript
{
    "1" : {
        id: 1,
        key: 'share',
        description: '分享',
        status: 1
     }
}
```

## 返回值详解

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| id | number | 当前配置项唯一的id |
| key | string | 当前配置项的名称 |
| description | string | 当前配置项的说明 |
| status | number | 当前配置项的状态， 1 - TRUE， 0 - FALSE |

