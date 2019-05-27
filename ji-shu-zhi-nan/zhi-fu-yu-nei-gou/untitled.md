# 支付回调

玩家支付成功之后，天幕平台会根据开发者提供的支付回调地址，通知开发者发货。 回调地址返回的参数中 `code` 为0即为成功。

天幕平台服务器通过 `POST` 请求开发者提供的支付回调地址通知发货。 开发者服务器需识别 `application/json` 类型的请求数据。

天幕强烈建议开发者服务端在实际发货前，通过 [订单有效性查询](https://www.yuque.com/eqrk37/gk0pcl/tv4sd9) 再次校验。

**平台http请求格式**

请识别以下请求head：

```text
{
    header: { //平台请求头的content-type
        'content-type': 'application/json'
    },
    data: { //平台请求参数
        orderCode: '',
        coin: '',
        param: '',
    }
}
```

**天幕平台请求的参数**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| orderCode | string | 天幕平台订单号 |
| coin | number | 用户购买的游戏币，一般为实付人民币\*10 \(单位：角\) |
| param | string | 对应客户端的参数，即发起支付时的 `program_param` |

**关于param**

**注意！param只用于前端透传的参数，资产校验请以coin字段返回数值为准，禁止使用回调接口的param校验金额。**

**回调参数**

```text
//正确回调
{
    "code": 0
    "msg": "",
    "data": {}
}
//错误回调
{
    "code": 非0,
    "msg": "",
    "data": {}
}
```

