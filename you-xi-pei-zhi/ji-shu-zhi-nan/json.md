# 在线参数

该接口主要用于获取在天幕后台配置的在线参数，本篇内容为技术说明文档，功能说明及配置方法请参阅：

{% page-ref page="../zhu-yao-gong-neng-shuo-ming/json.md" %}

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

