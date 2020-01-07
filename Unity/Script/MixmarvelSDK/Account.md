# Mixmarvel.MixmarvelSDK.Account

Mixmarvel账号体系相关API接口

------

1. **申请验证码**（注册和修改密码用）

调用代码：

```c#
MixmarvelSDK.Account.SendVertifyCode(userName, onSuccessCallBack, onFailCallBack);
```

参数列表：

| 参数 | 类型 | 功能 |
| --- | --- | --- |
| userName | string | 用户名 |
| onSuccessCallBack | Action<HttpProtoMessage> | 获取成功回调 |
| onFailCallBack | Action<HttpProtoMessage>  | 获取失败回调 |

------

2. **注册**

调用代码：

```c#
MixmarvelSDK.Account.Register(userName, password, vertifyCode, inviteCode, onSuccessCallBack , onFailCallBack);
```

参数列表：

| 参数 | 类型 | 功能 |
| --- | --- | --- |
| userName | string | 用户名 |
| password | string | 用户密码 |
| vertifyCode | string | 验证码 |
| inviteCode | string | 邀请码 |
| onSuccessCallBack |  Action<HttpProtoMessage>  | 注册成功回调 |
| onFailCallBack | Action<HttpProtoMessage> | 注册失败回调 |

------

3. **修改账户密码**

调用代码：

```c#
MixmarvelSDK.Account.ChangePassword(userName, password, vertifyCode, onSuccessCallBack , onFailCallBack);
```

参数列表：

| 参数 | 类型 | 功能 |
| --- | --- | --- |
| userName | string | 用户名 |
| password | string | 新用户密码 |
| vertifyCode | string | 验证码 |
| onSuccessCallBack |  Action<HttpProtoMessage>  | 注册成功回调 |
| onFailCallBack | Action<HttpProtoMessage> | 注册失败回调 |

------

4. **登录**

调用代码：

```c#
MixmarvelSDK.Account.LoginSDK(userName, password, onSuccessCallBack, onFailCallBack);
```


参数列表：

| 参数 | 类型 | 功能 |
| --- | --- | --- |
| userName | string | 用户名 |
| password | string | 密码 |
| onSuccessCallBack | Action | 登录成功回调 |
| onFailCallBack | Action<string,string> | 获取失败回调,第一个参数为错误码，第二个参数为错误描述信息 |

------

5.  **登出**

调用代码：

```c#
MixmarvelSDK.Account.LogoutSDK();
```


参数列表：

| 参数 | 类型 | 功能 |
| --- | --- | --- |
| - | - | - |

------

