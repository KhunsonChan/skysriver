# 在线参数

{% hint style="info" %}
该接口用于获取天幕配置的在线参数配置
{% endhint %}

## **调用方法**

```javascript
wx.tmSDK.getAppJSONConfig().then((res) => {
    console.log('在线配置参数:', res);
});
```

## 通过指定key获取制定配置

```javascript
wx.tmSDK.getAppJSONConfig('key').then((res) => {
    console.log('在线配置 key 对应的配置:', res);
});
```

