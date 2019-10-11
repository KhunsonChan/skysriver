# 在线参数 （.getAppJSONConfig）

`getAppJSONConfig`接口主要用于获取在天幕后台配置的在线参数，本篇内容为技术说明文档，功能说明及配置方法请参阅：

{% page-ref page="../main-features/json.md" %}

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

上述的【key】对应为在线参数配置后台中的【参数ID】，将【参数ID】作为传入参数即可获取到对应ID的配置内容，具体可参考下方的【返回值说明】。

## 返回值说明

![](../../.gitbook/assets/image%20%288%29.png)

根据你传入的参数不同，我们会返回不同的内容，请根据实际使用情况进行调整，以下为具体说明：

#### 当传入的参数为空时

在线参数配置后台如上图所示，参数为空时，会默认将该游戏下配置的所有【参数值Jason】中的内容返回。

若配置的内容与实际需求的不相符，请在在线参数配置后台进行修改。

#### 当传入的参数为【参数ID】字段值时

将在线参数后台的【配置ID】字段值作为传入参数，会将该ID所对应【参数值Jason】的内容返回。

