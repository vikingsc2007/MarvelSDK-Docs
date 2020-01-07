# Mixmarvel.MixmarvelSDK.Wallet

Mixmarvel钱包模块，负责调用Layer2状态机，及获取相关资产信息

------

1. **查询钱包地址**

调用代码示例：

```c#
MixmarvelSDK.Wallet.GetAllAddress(recvData =>
{
        for (int i = 0; i < recvData.Length; i++)
        {
            Debug.Log(i+". "+recvData[i].ToString());
        }
});
```

参数列表：

| 参数 | 类型 | 功能 |
| --- | --- | --- |
| onGotten | MixmarvelSDK.MixmarvelCallBackSuccess<WalletChainAddress[]> | 查询成功回调方法 |
| onError | MixmarvelSDK.MixmarvelCallBackFailed | 失败回调 |


查询之后也可以通过数据模块接口获取对应链的地址

```
MixmarvelSDK.Data.walletData.GetAddress(ChainType.Rocket);
```

**注意**：**登录后会自动拉取**一次地址列表，如无必要无需调用拉取。



------



2. **创建公链钱包地址**



调用代码示例：

```c#
MixmarvelSDK.Wallet.GenerataAddress(ChainType.ETH , recvData =>
{
    Debug.Log(recvData.address);
});
```

参数列表：

| 参数 | 类型 | 功能 |
| --- | --- | --- |
| onCreated | MixmarvelSDK.MixmarvelCallBackSuccess<WalletChainAddress> | 创建回调方法 |
| onError | MixmarvelSDK.MixmarvelCallBackFailed | 失败回调 |



------



3. **提现公链币**



调用代码示例：

```c#
 MixmarvelSDK.Wallet.WithdrawBnt(TokenType.ETH,"0xEB1fB46b773dc00cdD1fE37B461BD186983e19eA","12.123", recvData =>
        {
            Debug.Log("成功调用");
        });
```

参数列表：

| 参数         | 类型                                                  | 功能         |
| ------------ | ----------------------------------------------------- | ------------ |
| tokenType    | TokenType                                             | 公链币类型   |
| address      | address                                               | 提现到该地址 |
| balance      | balance                                               | 提现数额     |
| onWithDrawed | MixmarvelSDK.MixmarvelCallBackSuccess<BntBalanceInfo> | 提现完成回调 |
| onError      | MixmarvelSDK.MixmarvelCallBackFailed                  | 失败回调     |



------



4. **提现FT币**



调用代码示例：

```c#
 MixmarvelSDK.Wallet.WithdrawFt("0xEB1fB46b773dc00cdD1fE37B461BD186983e19eA","0xEB1fB46b773dc00cdD1fE37B461BD186983e19eA","12.123", recvData =>
        {
            Debug.Log("成功调用");
        });
```

参数列表：

| 参数         | 类型                                                 | 功能         |
| ------------ | ---------------------------------------------------- | ------------ |
| assetTypeId  | string                                               | FT币类型     |
| address      | string                                               | 提现到该地址 |
| balance      | string                                               | 提现数额     |
| onWithDrawed | MixmarvelSDK.MixmarvelCallBackSuccess<FtBalanceInfo> | 提现完成回调 |
| onError      | MixmarvelSDK.MixmarvelCallBackFailed                 | 失败回调     |



------





5. **提现NFT资产**



调用代码示例：

```c#
 MixmarvelSDK.Wallet.WithdrawNft("0x31adwdawd12312d","0xEB1fB46b773dc00cdD1fE37B461BD186983e19eA","0xEB1fB46b773dc00cdD1fE37B461BD186983e19eA","135131", recvData =>
        {
            Debug.Log("成功调用");
        });
```

参数列表：

| 参数         | 类型                                            | 功能           |
| ------------ | ----------------------------------------------- | -------------- |
| type         | ChainType                                       | 提现目标链类型 |
| assetTypeId  | string                                          | NFT币类型      |
| address      | string                                          | 提现到该地址   |
| tokenId      | string                                          | 提现token      |
| onWithDrawed | MixmarvelSDK.MixmarvelCallBackSuccess<JsonData> | 提现完成回调   |
| onError      | MixmarvelSDK.MixmarvelCallBackFailed            | 失败回调       |



------



5. **调用layer2状态机接口**



调用代码示例：

```c#
 MixmarvelSDK.Wallet.CallStateMachine(
    MixmarvelSDK.Data.platformData.appId/*平台的状态机的id，其他游戏填自己的*/,
    "{aa:"111"}"/*传递给状态机调用的参数*/,
    TransferPackData.Alloc().SetBnt(TokenType.ETH,"11").AddNft("0xaaabbbccc","12351"),
    recvData =>
    {     
        Debug.Log("成功调用");
		});

```

参数列表：

| 参数               | 类型                                            | 功能           |
| ------------------ | ----------------------------------------------- | -------------- |
| appId              | string                                          | 提现目标链类型 |
| payload            | string                                          | NFT币类型      |
| transfer           | TransferPackData                                | 提现到该地址   |
| onCallStateMachine | MixmarvelSDK.MixmarvelCallBackSuccess<JsonData> | 调用回调       |
| onError            | MixmarvelSDK.MixmarvelCallBackFailed            | 失败回调       |





------





6. **获取公链币Layer2余额**



调用代码示例：

```c#
MixmarvelSDK.Wallet.GetRocketBntBalance(
    TokenType.ETH,
    MixmarvelSDK.Wallet.selfRocketAddress,
    balanceInfo =>
    {
        Debug.Log(balanceInfo.tokenType.fullName + ":" +balanceInfo.balance);
    });

```

参数列表：

| 参数      | 类型                                                  | 功能           |
| --------- | ----------------------------------------------------- | -------------- |
| tokenType | TokenType                                             | 提现目标链类型 |
| address   | string                                                | NFT币类型      |
| onSuccess | MixmarvelSDK.MixmarvelCallBackSuccess<BntBalanceInfo> | 提现到该地址   |
| onFail    | MixmarvelSDK.MixmarvelCallBackFailed                  | 失败时回调     |

此接口也可以查询其他所有人的余额



------



7. **获取FT币Layer2余额**



调用代码示例：

```c#
MixmarvelSDK.Wallet.GetRocketFtBalance(
    ”0xaaaddawdadw“,
    MixmarvelSDK.Wallet.selfRocketAddress,
    balanceInfo =>
    {
        Debug.Log(balanceInfo.setId + ":" +balanceInfo.balance);
    });

```

参数列表：

| 参数      | 类型                                                 | 功能                 |
| --------- | ---------------------------------------------------- | -------------------- |
| tokenType | string                                               | FT币类型             |
| address   | string                                               | 查询的layer2账号地址 |
| onSuccess | MixmarvelSDK.MixmarvelCallBackSuccess<FtBalanceInfo> | 成功时回调           |
| onFail    | MixmarvelSDK.MixmarvelCallBackFailed                 | 失败时回调           |

此接口也可以查询其他所有人的余额



------



8. **获取余额大于0的所有FT币Layer2余额**



调用代码示例：

```c#
MixmarvelSDK.Wallet.GetRocketFtBalanceGreatZero(
    MixmarvelSDK.Wallet.selfRocketAddress,
  	2,
  	100,
    balanceInfos =>
    {
      	for(int i = 0; i<balanceInfos.Length;i++)
        {
          Debug.Log(balanceInfos[i].setId + ":" +balanceInfos[i].balance);
        }
        
    });

```

参数列表：

| 参数      | 类型                                                   | 功能                 |
| --------- | ------------------------------------------------------ | -------------------- |
| address   | string                                                 | 查询的layer2账号地址 |
| pageNo    | int                                                    | 查询页码             |
| pageSize  | int                                                    | 成功时回调           |
| onSuccess | MixmarvelSDK.MixmarvelCallBackSuccess<FtBalanceInfo[]> | 成功时回调           |
| onFail    | MixmarvelSDK.MixmarvelCallBackFailed                   | 失败回调             |

此接口也可以查询其他所有人的余额



------



9. **获取拥有的某种的NFT的Layer2数量**



调用代码示例：

```c#
MixmarvelSDK.Wallet.GetRocketNftCount(
    "0xaaaaaaaa",
  	MixmarvelSDK.Wallet.selfRocketAddress,
    count =>
    {
          Debug.Log("0xaaaaaaaa" + ":" +count);
    });

```

参数列表：

| 参数      | 类型                                       | 功能                 |
| --------- | ------------------------------------------ | -------------------- |
| setId     | string                                     | 查询的NFT类型        |
| address   | string                                     | 查询的layer2账号地址 |
| onSuccess | MixmarvelSDK.MixmarvelCallBackSuccess<int> | 成功回调             |
| onFail    | MixmarvelSDK.MixmarvelCallBackFailed       | 失败回调             |

此接口也可以查询其他人的所有余额



------



10. **获取拥有的某种的NFT的信息列表**



调用代码示例：

```c#
MixmarvelSDK.Wallet.GetRocketNftList(
    "0xaaaaaaaa",
    MixmarvelSDK.Wallet.selfRocketAddress,
  	2,
  	100,
    tokens =>
    {
        for(int i = 0; i<tokens.Length;i++)
        {
          Debug.Log(tokens[i].setId + ":" +tokens[i].tokenId);
        }
    });

```

参数列表：

| 参数      | 类型                                                  | 功能                 |
| --------- | ----------------------------------------------------- | -------------------- |
| setId     | string                                                | 查询的NFT类型        |
| address   | string                                                | 查询的layer2账号地址 |
| pageNo    | int                                                   | 查询页码             |
| pageSize  | int                                                   | 查询页的尺寸         |
| onSuccess | MixmarvelSDK.MixmarvelCallBackSuccess<NftTokenInfo[]> | 成功时回调           |
| onFail    | MixmarvelSDK.MixmarvelCallBackFailed                  | 失败回调             |

此接口也可以查询其他所有人的余额



------



11. **获取某个NFT的Token的详细信息**



调用代码示例：

```c#
MixmarvelSDK.Wallet.GetRocketNftInfo(
    "0xaaaaaaaa",
  	MixmarvelSDK.Wallet.selfRocketAddress,
    tokens =>
    {
        for(int i = 0; i<tokens.Length;i++)
        {
          Debug.Log(tokens[i].setId + ":" +tokens[i].tokenId);
        }
    });

```

参数列表：

| 参数      | 类型                                                | 功能                 |
| --------- | --------------------------------------------------- | -------------------- |
| setId     | string                                              | 查询的NFT类型        |
| tokenId   | string                                              | 查询的layer2账号地址 |
| onSuccess | MixmarvelSDK.MixmarvelCallBackSuccess<NftTokenInfo> | 成功时回调           |
| onFail    | MixmarvelSDK.MixmarvelCallBackFailed                | 失败回调             |

此接口也可以查询其他所有人的余额


