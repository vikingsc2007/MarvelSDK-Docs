# Mixmarvel.MixmarvelSDK.UI

Mixmarvel SDK For Unity 提供的预制UI，通过接口打开关闭。

1. **打开登录注册界面**

调用代码：

```c#
MixmarvelSDK.UI.OpenLoginWnd();//打开登录界面
MixmarvelSDK.UI.CloseLoginWnd();//关闭登录界面
```

参数列表：

| 参数 | 类型 | 功能 |
| --- | --- | --- |
| - | - | - |

登录成功登录界面后会自动关闭, 登录成功可以通过event事件捕获，捕获后可以通过数据模块获得账号信息,示例代码如下

```c#
MixmarvelSDK.Account.OnLoginSuccess += ()=>{ 
	Debug.Log(MixmarvelSDK.Data.platformData.uid);
	Debug.Log(MixmarvelSDK.Data.platformData.token);
	Debug.Log(MixmarvelSDK.Data.platformData.openid);
}
```

------
