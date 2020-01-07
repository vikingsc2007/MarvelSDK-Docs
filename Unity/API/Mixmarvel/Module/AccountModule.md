# Class AccountModule



**命名空间**:Mixmarvel.Module

**继承父类**:TMonoSingleton<AccountModule>



## 说明

实现账号模块功能的单例类

##成员

| 属性           | 类型           | 介绍             |
| -------------- | -------------- | ---------------- |
| HaveCache   | bool   | 是否有上次登录后缓存的账号信息，如果有可以快速登录     |
| cachedUid     | long     | 上次成功登录后缓存的平台账号唯一标识     |
| cachedToken     | string     | 上次成功登录后缓存的平台账号token      |
| loginState | LoginState | 登录状态 |

| 公共方法    | 介绍 |
| ---- | -------- |
| [QueryUserSimpleInfo](AccountModule/QueryUserSimpleInfo.md)    | 查询用户名及头像 |
| SendVertifyCode    | 获取注册验证码 |
| Register    | 注册账号 |
| ChangePassword    | 修改密码 |
| LoginSDK    | 登录 |
| LoginSDKAuto    | 使用缓存的账号信息快速登录 |
| LogoutSDK    | 登出SDK |
| PasswordReVertify    | 密码二次验证 |

