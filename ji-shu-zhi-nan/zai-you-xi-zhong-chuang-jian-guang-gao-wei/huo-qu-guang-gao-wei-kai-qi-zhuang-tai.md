# 获取广告位开启状态

### **checkFlowIsOpen**

该接口用于获取天幕后台配置是否开启

#### **注意**

使用该接口前，请先进行[SDK初始化](https://skysriver.gitbook.io/skysriver/ji-shu-zhi-nan/chu-shi-hua-ni-de-sdk)

### **调用方法**

```java
wx.tmSDK.checkFlowIsOpen({
     positionId: positionId
}).then(({ isOpen }) => {
    console.log('该广告位是否开启:', isOpen);
});
```

### **传入参数**

| 字段 | 字段类型 | 说明 |
| :--- | :--- | :--- |
| positionId | string | 广告位id |

### **返回值样例**

```java
{
    isOpen: true,
    type: 1,
}
```

### **返回参数**

| 字段 | 字段类型 | 说明 |
| :--- | :--- | :--- |
| isOpen | boolean | 广告位是否开启 |
| type | string | 广告位类型, 仅当isOpen为true时，才有值 |

