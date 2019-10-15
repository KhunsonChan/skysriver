---
description: 分析微信banner广告自加载到展示到点击的完全流程
---

# banner分析

{% hint style="info" %}
banner分析需接入天幕SDK中微信广告分析的方法方可统计，可按需接入。详见：[微信广告分析](https://doc.skysriver.com/game-data/dev-guide/official-ad-analysis)。

banner分析数据菜单提供了banner广告从加载到展示再到点击全流程的数据，同时还提供了错误，帮助开发与运营人员了解banner广告情况，协助广告收益调优。
{% endhint %}

* 活跃用户：进入小程序或者小游戏的用户数，同一用户同周期多次访问不重复记录（需要接入天幕SDK登录功能，所以与官方略有出入）
* 新增用户：首次登录小程序或者小游戏的用户数，同一用户多次访问不重复记录
* 加载次数：banner广告加载的次数，即广告接口load请求次数
* 展示次数：banner广告展示曝光的次数，即广告接口show请求次数
* 点击次数：banner广告被用户点击的次数
* 新用户点击：应用的新增用户点击banner广告的次数
* 官方曝光：官方后台给出的曝光次数，数据可在游戏收支-微信收入管理上传
* 官方点击：官方后台给出的点击次数，数据可在游戏收支-微信收入管理上传
* 收入：来自微信banner广告的收入，可在游戏收支-微信收入管理后台中上传

{% hint style="warning" %}
官方曝光、官方点击以及收入可在游戏收支中上传后展示，详情请参考[游戏收支](https://doc.skysriver.com/general-function/revenue)。
{% endhint %}

