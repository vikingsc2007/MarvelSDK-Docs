# Class MixmarvelConfig

**命名空间**:Mixmarvel

**继承父类**:UnityEngine.MonoBehaviour

## 说明

Mixmarvel配置脚本，挂载在初始场景上用于调整SDK相关配置信息。

## 静态成员

| 静态属性    | 类型 | 介绍 |
| ---- | -------- |-------- |
| AppId    | string | 配置APPID，如果不配置，则必须在初始化SDK时手动传入，若配置，则不需要传入 |
| platfomServer    | string |平台websocket服务器地址，平台推送专用 |
| platfomHttpServer    | string |平台Http服务器地址 |
| walletServer    | string |钱包websocket服务器地址，钱包连接专用 |
| walletHttpServer    | string |钱包Http服务器地址 |
| walletPingTm    | string |钱包心跳间隔时间，默认为5s |
| notificationPingTm    | string |推送心跳间隔时间 ，默认为5s |
| allowProtoBackMaxTm    | float | 协议返回最大超时时间，超过则触发断线重连逻辑 |
| useWalletService    | bool |是否开启钱包服务，默认为true |
| usePushNotification    | bool |是否使用平台消息推送，如开启，将有一条websocket连接用于通知平台服务器推送，如聊天和邮件，默认为true |
| useLocalConfigPlatfomServer    | bool |是否强制使用配置的平台服务器地址，默认为false，服务器地址在登录时自动获取 |
| useLocalConfigWalletServer    | bool |是否强制使用配置的钱包服务器地址，默认为false，服务器地址在登录时自动获取  |

## 成员

暂无