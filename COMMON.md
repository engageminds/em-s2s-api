# Common Defines

## BasicFields

| Name    | Type                  | Explain                                                              | Example                              | iOS | Android |
|---------|-----------------------|----------------------------------------------------------------------|--------------------------------------|-----|---------|
| ts      | int64                 | 客户端时间,单位毫秒                                                           | 1567479919643                        | ✔︎  | ✔︎      |
| fit     | int32                 | 客户端首次安装App时间,单位秒                                                     | 1567479919                           | ✔︎  | ✔︎      |
| flt     | int32                 | 客户端首次打开App时间,单位秒(uid文件创建时间)                                          | 1567479919                           | ✔︎  | ✔︎      |
| zo      | int32                 | 时区偏移量,单位分钟. 比如北京时区 zo=480                                            | 480                                  | ✔︎  | ✔︎      |
| tz      | string                | TimeZone.getDefault().getID()                                        | Asia/Shanghai︎                       | ✔︎  | ✔︎      |
| session | string                | SessionID                                                            | BBD6E1CD-8C4B-40CB-8A62-4BBC7AFE07D6 | ✔︎  | ✔︎      |
| uid     | string                | 用户ID, SDK生成的唯一用户ID                                                   | BBD6E1CD-8C4B-40CB-8A62-4BBC7AFE07D6 | ✔︎  | ✔︎      |
| ssid    | string                | em 生成并下发                                                             | 28A29uDTOAcTEOs7IbHUyg               | ✖︎  | ✖︎      |
| gaid    | string                | GAID                                                                 | bbd6e1cd-8c4b-40cb-8a62-4bbc7afe07d6 | ✖︎  | ✔︎      |
| idfa    | string                | IDFA                                                                 | BBD6E1CD-8C4B-40CB-8A62-4BBC7AFE07D6 | ✔︎  | ✖︎      |
| idfv    | string                | IDFV                                                                 | BBD6E1CD-8C4B-40CB-8A62-4BBC7AFE07D6 | ✔︎  | ✖︎      |
| oaid    | string                | OAID                                                                 | BBD6E1CD-8C4B-40CB-8A62-4BBC7AFE07D6 | ✖︎  | ✖︎      |
| dtype   | uint8                 | [设备类型](#dtypes)                                                      | 1                                    | ✔︎  | ✔︎      |
| lang    | string                | 手机语言code                                                             | en_US                                | ✔︎  | ✔︎      |
| jb      | uint8                 | jailbreak 状态, 0:正常,1:越狱                                              | 1                                    | ✖︎  | ✖︎      |
| bundle  | string                | 当前App包名                                                              | com.xxx.xxx                          | ✔︎  | ✔︎      |
| make    | string                | 手机生产商                                                                | huawei                               | ✖︎  | ✔︎      |
| brand   | string                | 手机品牌                                                                 | huawei                               | ✖︎  | ✔︎      |
| model   | string                | 手机型号                                                                 | iPhone10,3                           | ✔︎  | ✔︎      |
| os      | uint8                 | 操作系统, 0:iOS,1:Android,2:HarmonyOS,3:MacOS,4:Windows,5:Linux          | 1                                    | ✔︎  | ✔︎      |
| osv     | string                | 系统版本号                                                                | 12.1                                 | ✔︎  | ✔︎      |
| appk    | string                | AppKey                                                               | wcx123412vzxcvaACsddq2               | ✔︎  | ✔︎      |
| appv    | string                | 当前App版本号                                                             | 1.0                                  | ✔︎  | ✔︎      |
| sdk     | uint8                 | 当前SDK类型, 0:iOS,1:Android,2:JS,3:ServerJava,4:ServerGo,5:ServerPython | 1                                    | ✔︎  | ✔︎      |
| sdkv    | string                | 当前SDK版本号                                                             | 1.0                                  | ✔︎  | ✔︎      |
| width   | uint32                | 屏幕宽度(像素)                                                             | 1028                                 | ✔︎  | ✔︎      |
| height  | uint32                | 屏幕高度(像素)                                                             | 2094                                 | ✔︎  | ✔︎      |
| contype | uint8                 | 当前网络类型 [ConnectionType](#connectiontype)                             | 4                                    | ✔︎  | ✔︎      |
| carrier | string                | 运营商名称, NetworkOperatorName                                           | 中国移动                                 | ✔︎  | ✔︎      |
| mccmnc  | string                | 运营商mcc+mnc, NetworkOperator                                          | 46002                                | ✔︎  | ✔︎      |
| gcy     | string                | TelephonyManager.getNetworkCountryIso()                              | cn                                   | ✖︎  | ✖︎      |
| sco     | uint8                 | 屏幕方向, 0:unknown,1:portrait,2:landscape                               | 1                                    | ✔︎  | ✔︎      |
| adtk    | uint8                 | ad_tracking_enable, 0:No,1:Yes                                       | 1                                    | ✖︎  | ✖︎      |
| ntf     | uint8                 | 是否开启通知, 0:No,1:Yes                                                   | 0                                    | ✖︎  | ✖︎      |
| gp      | uint8                 | 是否安装GP, 0:No,1:Yes                                                   | 0                                    | ✖︎  | ✔︎      |
| bps     | map&lt;string,any&gt; | 自定义基础属性                                                              | {"a":1}                              | ✖︎  | ✖︎      |

## DTypes

| Value | Description |
|-------|-------------|
| 0     | Unknown     |
| 1     | Phone       |
| 2     | Tablet      |
| 3     | TV          |
| 4     | PC          |

## ConnectionType

> Copy
> From "[OpenRTB API Specification Version 2.5](https://www.iab.com/wp-content/uploads/2016/03/OpenRTB-API-Specification-Version-2-5-FINAL.pdf)"
> Page 52

| Value | Description                           |
|-------|---------------------------------------|
| 0     | Unknown                               |
| 1     | Ethernet                              |
| 2     | WIFI                                  |
| 3     | Cellular Network – Unknown Generation |
| 4     | Cellular Network – 2G                 |
| 5     | Cellular Network – 3G                 |
| 6     | Cellular Network – 4G                 |
| 7     | Cellular Network – 5G                 |

## Error

| Type                   | Description          |
|------------------------|----------------------|
| EventTimeOverRange     | 事件时间超出允许范围(前7天到后1小时) |
| EventInvalid           | 事件名非法                |
| EventTooLong           | 事件名超长                |
| EventUndefined         | 事件属性未定义              |
| PropTooLong            | 事件属性名超长              |
| PropInvalid            | 事件属性名非法              |
| PropUndefined          | 事件属性未定义              |
| PropInconsistent       | 事件属性值类型错误            |
| PropTruncated          | 事件属性值超长截断            |
| StaticPropInconsistent | 公共事件属性值类型错误          |
| StaticPropTruncated    | 公共事件属性值超长截断          |
| UserPropTooLong        | 用户属性名超长              |
| UserPropInvalid        | 用户属性名非法              |
| UserPropInconsistent   | 用户属性值类型错误            |
| UserPropUndefined      | 用户属性未定义              |
| UserPropTruncated      | 用户属性值超长截断            |


