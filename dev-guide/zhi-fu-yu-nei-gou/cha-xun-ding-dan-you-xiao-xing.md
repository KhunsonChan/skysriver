# 查询订单有效性

{% hint style="info" %}
天幕强烈建议开发者服务端在实际发货前，调用此接口检查再次校验订单的有效性。
{% endhint %}

### **请求地址**

| 方法 | 请求地址 |
| :--- | :--- |
| GET | https://api.kuaiyugo.com/api/payment/v1/check\_order\_validities |

### **请求参数**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| order\_code | string | 天幕平台订单号 |
| coin | number | 用户购买的游戏币 \(单位：角\) |
| param | string | 对应客户端的参数，即发起支付时的 `program_param` |

### **返回参数**

| 字段 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| err | number | 状态码，0代表查询成功，非0代表查询异常 |
| data | object | 返回数据 |
| data.is\_valid | boolean | 订单信息是否合法，true合法，false非法 |
| msg | string | 状态码描述 |

### **返回参数示例**

```java
{
    "err": 0,
    "data": {
        "is_valid": true
    },
    "msg": "请求成功"
}
```



