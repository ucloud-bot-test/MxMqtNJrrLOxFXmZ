# 获取GlobalSSH价格 - GetGlobalSSHPrice

## 简介

获取GlobalSSH价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetGlobalSSHPrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetGlobalSSHPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID,如org-xxxx。请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **Quantity** | int | 购买周期，如果ChargeType为Month，Quantity默认为0；其他情况必须为大于0的整数 |No|
| **ChargeType** | string | 计费类型：Dynamic，Month，Year |No|
| **InstanceType** | string | 版本类型。枚举值，Enterprise:企业版；Basic:基础版。可不填，默认为Basic。  |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | float | 价格,返回单位为元 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetGlobalSSHPrice
&ProjectId=org-xxxx
&InstanceType=Basic
&Quantity=1
&ChargeType=Year
```

### 响应示例
    
```json
{
  "Action": "GetGlobalSSHPriceResponse",
  "Price": 90,
  "RetCode": 0
}
```





