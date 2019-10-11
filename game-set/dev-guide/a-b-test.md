# A/B test （.abtest）

本篇将说明如何接入天幕的A/B test功能，关于后台的设置，请参阅：[A/B test设置。](../main-features/ab-test.md)

具体的位置为：游戏配置-&gt; 选择游戏-&gt; A/B test。

#### 使用示例

使用前，请在【游戏配置-A/B test 】中创建相关的测试计划。传入需要接入的测试计划ID 即plan\_id。

```javascript
let plan_id = 22;
wx.tmSDK.abtest(plan_id).then(res => {
    console.log(res);
});
```

#### 返回值说明

传入测试计划ID后，会返回在对应计划下当前用户所属的策略组ID `group_id`

返回值的格式如下：

```javascript
{
   "planId": "123",
   "groupId": "group1"
}
    // 不存在则返回：{}
```

注意：若传入的`plan_id`不存在，会返回空值。

