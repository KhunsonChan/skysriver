---
description: 组件化接入说明，建议详细阅读
---

# 组件化方式接入广告位

## 接入方式说明

目前天幕广告位接入的方式有两种：

1. 组件化的方式接入（仅支持cocos、laya引擎）
2. api的方式接入

| 广告位类型 | **组件化接入** | API接入 |
| :--- | :--- | :--- |
| 多Icon广告位 | 支持 | 支持 |
| 浮动窗广告位 | 支持 | 支持 |
| 插屏广告位 | 支持 | 不支持 |
| 伪视频广告位 | 支持 | 不支持 |
| Banner广告位 | 不支持 | 支持 |

{% hint style="warning" %}
我们建议优先使用组件化的方式接入广告位：

1. 若你的游戏引擎非cocos，laya
2. 或是组件的样式不满足需求（此情况常见于[多Icon广告位](createflow/more-icon.md#zu-jian-yang-shi)）

SDK组件无法满足，则可通过[API的方式接入](../api/)。
{% endhint %}

通过组件化的形式接入，请继续阅读下方的内容。

{% hint style="info" %}
接入广告位时，所需要的广告位ID（positionID），请在“[卖量助手-流量主游戏管理](../../main-features/flower-game-manage.md#guang-gao-wei-guan-li)”中获取。
{% endhint %}

## 获取广告位开关状态

天幕的所有广告位支持后台控制其开/关，具体可参阅

{% page-ref page="../ad-position-status.md" %}

## 组件化接入——creatFlow组件

确定广告位开启后，调用creatFlow组件完成渲染，具体可参阅

{% page-ref page="createflow/" %}



