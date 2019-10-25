# 分享素材配置

## 概述

本篇为转发素材配置的开发说明，功能说明请参阅：[分享素材配置-功能说明](../../main-features/sharing-management.md)

## **分享位**

同一小程序/小游戏中，不同位置/功能下的分享，需要配置不同的内容。

天幕中，将这些位置/功能作为不同的分享位进行管理。

![&#x4E0A;&#x56FE;&#x53EF;&#x505A;&#x4E3A;&#x4E09;&#x4E2A;&#x4E0D;&#x540C;&#x7684;&#x5206;&#x4EAB;&#x4F4D;&#x8FDB;&#x884C;&#x7BA1;&#x7406;](https://cdn.kuaiyugo.com/plat/cms/plat/2019-02-20_4d8e3760-34bd-11e9-8a41-695d0962f26d.png)

一款小游戏中的分享场景举例：

| 分享位 | 说明 | 分享位ID |
| :--- | :--- | :--- |
| 右上角分享 | 用户点击右上角...发起分享 | initiative |
| 首页邀请 | 在首页邀请好友 | indexInvite |
| 结束页邀请 | 死亡后邀请好友比拼 | gameoverInvite |
| 战绩分享 | 获得历史最高分后炫耀战绩 | highscore |

## **分享引入逻辑**

涉及到邀请好友对战等分享引入逻辑时，开发者可以在分享路径 `path` 中添加参数。

用户通过分享卡片进入小程序时，开发者可根据路径中的参数进行业务处理。

常见的使用场景案例：

* 邀请好友对战
* 好友通过分享进入时能获得奖励
* 通过分享拉新后，发起分享者可以获得奖励

## **接入**

以下是分享素材功能使用的三个接口

{% hint style="info" %}
强烈建议参照[开发demo](../../../selling/dev-guide/dev-demo.md)，完成接入
{% endhint %}

1.用户点击右上角菜单的转发按钮时调用

{% page-ref page="onshareappmessage.md" %}

2.小游戏主动分享时调用

{% page-ref page="shareappmessage.md" %}

3.一次性接收所有分享位的分享素材相关数据（可选，非必接）

{% page-ref page="getsharetemplates.md" %}

