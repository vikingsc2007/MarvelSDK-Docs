# Function QueryUserSimpleInfo

## 参数列表


| 参数           | 类型           | 介绍             |
| -------------- | -------------- | ---------------- |
| uid   | long   | 要查询的账号uid     |
| callback     | Action<string,string,string>     | 查询返回回调，回调函数，参数 username，nickname，icon  |


## 说明

根据uid查询玩家的头像，昵称，用户名三个简单信息。


```c#
MixmarvelSDK.Account.QueryUserSimpleInfo(uid, (userName, nickName, icon) =>
{
	var _userName = userName;
    var _nickName = nickName;
    var _icon = icon;
});

```