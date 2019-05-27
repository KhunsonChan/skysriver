# 技术指南



##  <a id="article-title"></a>

该接口用于初始化SDK，可配置当前应用的版本号等，某些接口必须初始化SDK之后才能使用

**关联接口**

* [onShareAppMessage](https://www.yuque.com/eqrk37/gk0pcl/ntp4sq)
* [shareAppMessage](https://www.yuque.com/eqrk37/gk0pcl/in50nh)
* [createFlow](https://www.yuque.com/eqrk37/gk0pcl/gpcbyk)
* [checkFlowIsOpen](https://www.yuque.com/eqrk37/gk0pcl/xvu16v)
* [getFlowConfig](https://www.yuque.com/eqrk37/gk0pcl/okpygt)
* [getJudgeConfig](https://www.yuque.com/eqrk37/gk0pcl/tdc95r)

**调用方法**

调用.init方法实现，示例如下

```text
wx.tmSDK.init({
     hideRequestLog: false,
     appVersion: '1.0.0'
});
```

**传入参数**

| 字段 | 字段类型 | 说明 |
| :--- | :--- | :--- |
| hideRequestLog | boolean | 是否隐藏请求日志 |
| appVersion | string | 当前应用提交微信审核的版本号 |

