---
description: 该接口用于获取已经存放在天幕平台的用户信息，包含头像、昵称等。
---

# .login

该接口用于获取已经存放在天幕平台的用户信息，包含头像、昵称等。

请注意：若该接口返回值中无头像、昵称等微信信息，请调用 [updateUserinfo](update-userinfo.md) 更新用户信息。

## **调用方法**

```java
wx.tmSDK.login().then(res=>{
    console.log(res)
})
```

## **返回值样例**

```java
{
    "pid": "",
    "app_id": "wxa73fd8e544880e89",
    "open_id": "oc7L942AwAqIiBabNYb_cLl7mRsQ",
    "union_id": "",
    "nick_name": "",
    "avatar_url": "",
    "gender": 0,
    "city": "广州",
    "province": "广东省",
    "country": "中国",
    "language": "zh_CN",
    "gold": 0,
    "diamond": 0,
    "share_new": 0,
    "share_times": 0,
    "online_days": 0,
    "online_duration": 0,
    "last_login_time": 1551690740,
    "login_times": 1,
    "from_scene": "1044",
    "from_code": "ball-resurrection-1",
    "is_new": false,
    "ofp": "",
    "jwt": "",
    "login_province": "广东省",
    "login_city": "广州市",
    "login_district": "海珠区"
}
```

## **返回值详解**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| pid | string | 用户在星汉平台的统一索引，但可能变化 |
| app\_id | string | 应用的appid |
| open\_id | string | 用户在该应用下的openid |
| union\_id | string | 用户的unionid,默认为空字符串，绑定主体后大授权方可获得。[`绑定主体`](https://developers.weixin.qq.com/miniprogram/dev/api/uinionID.html) |
| nick\_name | string | 用户的微信昵称，为空时需要调用 `updateUserinfo` 获取 |
| nick\_name | string | 用户的微信昵称，为空时需要调用 `updateUserinfo` 获取 |
| avatar\_url | string | 用户的微信头像，为空时需要调用 `updateUserinfo` 获取 |
| gold | number | 用户在平台的金币数 |
| diamond | number | 用户在平台的钻石数 |
| is\_new | bool | 是否新注册的用户 |
| gender | number | 男：1 / 女：0 |
| language | string | 用户微信中设置的语言 |
| country | string | 用户微信中设置的国家 |
| province | string | 用户微信中设置的省份 |
| city | string | 用户微信中设置的城市 |
| login\_province | string | 根据用户ip判断用户所在的省份（注意：返回的省份名称与行政划分的名称一致，如西藏，返回的是西藏自治区。若要实现地区屏蔽功能，建议根据返回值前两位进行地区匹配） |
| login\_city | string | 根据用户ip判断用户所在的城市 |
| login\_district | string | 根据用户ip判断用户所在的区县 |
| share\_new | number | 用户在当前游戏的分享引入新用户的数量 |
| share\_times | number | 用户在当前游戏的分享次数 |
| online\_days | number | 用户在当前游戏在线的天数 |
| online\_duration | number | 累计在线时长（单位：秒） |



