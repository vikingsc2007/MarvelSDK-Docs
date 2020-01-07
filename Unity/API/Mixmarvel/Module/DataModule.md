# Class DataModule



**命名空间**:Mixmarvel.Module

**继承父类**:TMonoSingleton<DataModule>



## 说明

一个数据单单例类

##成员

| 属性           | 类型           | 介绍             |
| -------------- | -------------- | ---------------- |
| platformData   | PlatformData   | 平台数据信息     |
| walletData     | WalletData     | 钱包数据信息     |
| friendData     | FriendData     | 好友数据信息     |
| userCenterData | UserCenterData | 用户中心数据信息 |
| mailData       | MailData       | 邮件数据信息     |
| shopData       | ShopData       | 商店数据信息     |

| 静态属性    | 介绍 |
| ---- | -------- |
| S    | 获取单例 |



## 示例代码

```c#
WalletData walletData = Mixmarvel.Module.DataModule.S.walletData;
MailData mailData = Mixmarvel.Module.DataModule.S.mailData;
```

