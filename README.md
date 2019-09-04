---
description: 天幕是一个为小游戏开发者提供微信小游戏综合服务的平台
---

# 新手入门

![](.gitbook/assets/image%20%2898%29.png)

天幕是面向微信小游戏开发者/运营者的综合服务系统，主要功能为：买量助手、卖量助手、游戏数据、游戏配置，点击以上功能的名称可以进入详细的功能说明页面，以及具体的技术指南，可快速接入游戏使用。

小游戏开发者通过接入天幕sdk，不仅可以轻松进行卖卖量交易，通过天幕提供的小游戏的云端配置与强大实时的数据分析，还可以管理自己的小游戏矩阵，渠道合作等业务，告别繁琐，提升管理效率。

下方为天幕的一些基础信息说明。

## 天幕的账号体系

在加入天幕之前，请先了解如下天幕的账号体系相关内容。天幕账号可以创建多个主体，一个主体相当于公司内部的团体，可将游戏集中于该主体下进行统一管理。创建主体的用户默认为超级管理员，拥有该主体的全部权限。

您只需对天幕的账号体系有个大致的概念即可，后续我们会结合具体的业务场景进行解说。

## 加入天幕的方式

目前支持以下方式加入天幕：

1. 直接注册天幕账号；
2. 已有账号用户邀请加入；

### **直接注册天幕账号**

天幕已开放注册，用户可通过进入[天幕的官网](https://www.skysriver.com/)，点击右上角的注册按钮，使用手机号注册。

### **已有账号用户邀请加入**

已有账号用户登录天幕系统，创建主体后，可通过成员管理模块，点击添加成员，在弹出的页面填写成员手机号进行邀请。

请注意：

* 若成员已注册了天幕账号，重新登录后即可看见被邀请加入的主体；
* 若成员未注册天幕账号，则会收到一条带登录密码的手机短信，使用用户手机号+短信密码即可登录天幕系统；

## 账户角色

首先了解天幕中的角色，天幕主体下的账号角色分为三种：

1. 超级管理员；
2. 管理员；
3. 普通成员；

天幕将创建主体的账号默认赋予了超级管理员的权限，每个天幕主体拥有**1个超级管理员**，可设置**多个管理员**，加入**多个普通成员**。

### 角色权限

不同的角色所拥有的权限是不一样的。

#### **超级管理员**

1. 设置管理员；
2. 可将管理员、普通成员移出主体；
3. 设置管理员、普通成员查看游戏权限；
4. 查看主体下所有游戏的数据；
5. 为主体添加小游戏；

#### **管理员**

1. 将普通成员移出主体；
2. 设置普通成员查看游戏权限；
3. 查看主体下所有游戏的数据；
4. 为主体添加小游戏；

#### **普通成员**

为主体添加新游戏。

## 数据来源

天幕的数据是通过采集已接入天幕SDK的游戏数据。

天幕SDK采集的数据：

* 前端操作
* 后端日志
* 业务数据

目前接入天幕系统的方式为游戏客户端SDK接入。

### 数据安全

天幕始终将用户的数据安全视为最重要的事情，全力保障接入天幕系统的用户数据安全。

为了保障用户安全，天幕通过技术手段做了以下数据保障：

* 使用HTTPS作为传输协议
* 传输内容加密，确保采集过程中用户数据不暴露

通过前几篇内容的介绍，应该使您对天幕有了大致的了解，在后续我们会对天幕各功能进行讲解，您可继续浏览。

