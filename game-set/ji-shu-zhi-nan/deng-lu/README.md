# 登录



登录分为静默登录与用户授权信息登录。‌

### 静默登录 <a id="jing-mo-deng-lu"></a>

‌

用户打开小程序/小游戏时，默认进行静默登录，该功能由sdk集成，无需开发。‌

此时，开发者可以获取其微信唯一标识openid，用户处于已登录但未进行 **用户信息授权** 的状态。‌

静默登录过程中，用户无需点击任何按钮。‌

### **小游戏** <a id="xiao-you-xi"></a>

‌

仅静默登录（未授权）情况下，小游戏无法展示、获取用户头像与昵称。‌

但不影响记录用户的关卡记录、最高分、等级等游戏信息。‌

小游戏若没有展示用户头像昵称的需求，则可以只使用静默登录，来减少用户进入小游戏的交互。‌

### 用户信息授权 <a id="yong-hu-xin-xi-shou-quan"></a>

‌

相关api‌

* ​[login](https://skysriver.gitbook.io/skysriver/ji-shu-zhi-nan/deng-lu/shi-yong-login-huo-qu-deng-lu-yong-hu-xin-xi)​
* ​[updateUserInfo](https://skysriver.gitbook.io/skysriver/ji-shu-zhi-nan/deng-lu/cong-wei-xin-huo-qu-yong-hu-xin-xi)​

‌

小游戏需使用用户昵称、头像等微信信息时，需要进行用户信息授权。‌

这个过程也被称为 **大授权** 。‌

该过程要求用户在打开小游戏时，进行一次按钮点击操作。​![](https://cdn.nlark.com/yuque/0/2019/png/254569/1557223738363-224fac0f-90e6-4041-ad9a-f64e32df269d.png)‌

上图为小程序/小游戏向用户请求授权，该弹框由开发者自行渲染。‌

右侧弹框由微信渲染，不可更改。‌

### **完成授权** <a id="wan-cheng-shou-quan"></a>

‌

用户完成授权后，天幕平台会记录微信返回的头像、昵称等信息。‌

用户之后打开游戏时，开发者可以直接从天幕平台获取头像、昵称，因此不再需要用户点击授权按钮。‌

### **何时触发大授权** <a id="he-shi-chu-fa-da-shou-quan"></a>

‌

用户信息授权需要用户进行点击行为，可能会对用户流失率产生影响，因此策略上应该减少大授权的次数。大授权次数过少，可能会导致用户更换微信昵称、头像后，在小游戏中无法更新。‌

这里有几种策略可供参考。‌

#### **初次进入时大授权** <a id="chu-ci-jin-ru-shi-da-shou-quan"></a>

‌

仅在用户初次进入时进行大授权。 也就是在 [`login`](https://skysriver.gitbook.io/skysriver/ji-shu-zhi-nan/deng-lu/cong-wei-xin-huo-qu-yong-hu-xin-xi) 时，若返回值没有昵称、头像等信息，再使用 [`updateUserInfo`](https://skysriver.gitbook.io/skysriver/ji-shu-zhi-nan/deng-lu/cong-wei-xin-huo-qu-yong-hu-xin-xi) 向用户发起大授权。‌

若小游戏中需要使用用户头像、昵称，而不关心用户信息的更新（如用户换了昵称、头像），开发者可以采取该策略。‌

#### **定期大授权** <a id="ding-qi-da-shou-quan"></a>

‌

除了上述返回值没有昵称、头像的情况，一定要进行大授权以外，开发者可以自行确定大授权的频率，如每周一次、每月一次等等。‌

使用该方案，开发者可根据实际情况刷新用户信息，减少展示用户头像昵称时出现滞后的情况。‌

#### **不进行大授权** <a id="bu-jin-hang-da-shou-quan"></a>

‌

若小游戏中不展示用户昵称和头像，可以不进行大授权。 即使是初次进入的用户，也可以顺畅的直接开始游戏。‌

此外，需要头像、昵称的小程序/小游戏，可以通过以下方式规避大授权：‌

* 预置随机昵称
* 预置随机头像，如使用游戏角色图片作为用户头像
* 让用户自行设置昵称、头像、性别等信息

