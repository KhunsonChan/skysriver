# 业务流程

![image.png](https://cdn.nlark.com/yuque/0/2019/png/254569/1557224502093-5fd70323-f3f1-42db-8ee7-cce1e461dfb8.png)

注意， **10. 轮询请求支付结果** 中，游戏客户端需向开发者服务器轮询支付结果，做相应的业务处理。 建议3秒轮询请求一次支付结果，持续轮询2分钟。

#### 过程中：

* 小游戏客户端需调用 [`pay`](https://www.yuque.com/eqrk37/gk0pcl/elf7gv) 拉起支付
* 支付成功后，开发者服务端需接收 [支付回调](https://www.yuque.com/eqrk37/gk0pcl/lbp8es)
* 此外，天幕强烈建议开发者服务端在实际发货前，通过 [订单有效性查询](https://www.yuque.com/eqrk37/gk0pcl/tv4sd9) 再次校验

