# SDK更新日志

## 2.6.1 - 2019-07-23

### 新增

* UI对象新增onNavigate,可监听UI的跳转事件
* flowNavigate返回值新增navigateMessage字段,返回微信跳转信息

## 2.6.0 - 2019-07-11

### 新增

* 支持跳转微信小游戏的开发版、体验版。

## 2.5.2 - 2019-07-10

### 修复

* 修复浮动icon中多帧动图无法正常切换的bug

## 2.5.1 - 2019-07-08

### 修复

* 修复使用组件化创建广​告位时，无法监听onErr​or、onDestroy、onRender的bug。

## 2.5.0 - 2019-07-05

### 新增修复

* 新增AB test功能；

## 2.4.0 - 2019-06-28

### 新增

* 浮动窗广告位添加红点、角标；
* 多icon广告位添加红点、角标；
* 开放天幕设置banner广告位功能；

## 2.3.1 - 2019-06-24

### 新增

* 客服增加默认卡片发送功能

## 2.3.0 - 2019-06-21

### 新增

* 新增插屏广告UI组件渲染，支持laya与cocos

### 修复

* 修复浮动icon抖动的时候点击放大时位置偏移问题

### 变化

* getJudgeConfig接口传入id获取对应结果时，返回原始结构

## 2.2.0 - 2019-06-14

### 新增

* 新增天幕应用配置json下发
* 浮动广告新增边框渲染配置

## 2.1.3 - 2019-06-05

### 修复

* 防止旧接口appVersion传入为空影响内部appVersion问题

## 2.1.2 - 2019-06-03

### 修复

* 修复小程序环境下网络请求错误提示问题

## 2.1.1 - 2019-05-29

### 修复

* 支付要求appSecret的问题
* 无appSecret时日志无指纹问题

### 新增

* 支持使用ES5规范的代码结构

## 2.1.0 - 2019-05-15

### 修复

* 没有断网重试网络请求的问题
* 自定义事件修复增加成功与失败回调问题

### 新增

* 新增支持无appSecret应用的情况，支持开发者自行传入openId
* 分享加入支持自定义标题, getShareTempltes接口新增缓存所有模版
* 统一浮动窗广告的UI渲染和多icon广告渲染的坐标系，按照实际画布尺寸渲染，使用微信标准坐标系

### 变化

* updateUserInfo失败无用户名或头像时，从wx.getUserInfo中获取并返回
* getJudgeConfig接口优化，支持只传入id获取对应结果
* 域名校验优化，不校验备用域名
* 优化加载时长统计的调用时机

