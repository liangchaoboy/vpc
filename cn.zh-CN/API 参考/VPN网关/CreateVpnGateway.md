# CreateVpnGateway {#reference_i4w_xmt_ndb .reference}

创建一个VPN网关。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateVpnGateway

 |
|RegionId|String|是| VPN网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VpcId|String|是| VPN网关所属的VPC ID。

 |
|InstanceChargeType|String|否| VPN网关的计费类型，取值：

-   PREPAY：预付费，包月购买。

-   Postpay：后付费，按流量计费。


 |
|Period|Integer|否| 购买时长，取值：1-9 | 12 | 24 | 36

 |
|AutoPay|Boolean|否| 是否自动支付VPN网关的账单，取值：

 true | false \(默认值\)

 |
|Bandwidth|Integer|是| VPN网关的公网带宽，单位Mbps。取值：

 5 |10 | 20 | 50 | 100

 |
|EnableIpsec|Boolean|否| 是否开启IPsec-VPN功能。IPsec-VPN功能提供站点到站点的连接。您可以通过创建IPsec隧道将本地数据中心网络和专有网络或两个专有网络安全地连接起来。取值：

 true \(默认值\) | false

 |
|EnableSsl|Boolean|否| 开启SSL-VPN功能。提供点到站点的VPN连接，不需要配置客户网关，终端直接接入。取值：

 true | false \(默认值\)

 |
|SslConnections|Integer|否|允许同时连接的最大客户端数量。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|VpnGatewayId|String|VPN网关的ID。|
|Name|String|VPN网关的名称。|
|OrderId|String|订单ID，请前往阿里云控制台完成支付。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeNatGateways
&RegionId=cn-beijing
&&VpcId=vpc-bp1ub1yt9cvakoelj1y9c
&Bandwidth=5
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <CreateVpnGatewayResponse>
        <Name>myVpn</Name>
        <VpnGatewayId>vpn-bp1q8bgx4xnkm2ogj0fiu</VpnGatewayId>
        <RequestId>54B48E3D-DF70-471B-AA93-08E683A1B457</RequestId>
    </CreateVpnGatewayResponse>
    ```

-   JSON格式

    ```
    {
        "Name":"myVpn",
        "VpnGatewayId":"vpn-bp1q8bgx4xnkm2ogj0fiu",
        "RequestId"="54B48E3D-DF70-471B-AA93-08E683A1B457";
    }
    ```


