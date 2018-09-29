# CreateVSwitch {#reference_i4w_xmt_ndb .reference}

Create a VSwitch in the specified VPC.

When calling this interface to create a switch, note:

-   Up to 24 VSwitches can be created in a VPC.

-   The first and last three IP addresses of the VSwitch are reserved by the system. For example, if the CIDR block of a VSwitch is 192.168.1.0/24, IP addresses 192.168.1.0, 192.168.1.253, 192.168.1.254, and 192.168.1.255 are reserved.

-   The number of cloud product instances under the VSwitch cannot exceed the remaining capacity of the VPC \(subtract the current number of cloud product instances from 15,000\).

-   A cloud product instance can only belong to one VSwitch.

-   VSwitches do not support broadcasting or multicasting. After a VSwitch is created, its CIDR block cannot be modified.


## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required or not|Description|
|:---|:---|:--------------|:----------|
|Action|String|Yes| The action to perform. Value:

 CreateVSwitch

 |
|ZoneId|String|Yes| The ID of the zone to which the switch belongs.

 You can obtain the region ID by calling the DescribeZones API.

 |
|CidrBlock|String|Yes| The CIDR block of VSwitch. The IP address range must meet the following requirements:

 -   The size of the subnet mask for the VSwitch can be /16 to /29.
-   The CIDR block of the VSwitch must belong to the CIDR block of the VPC.
-   The CIDR block of the VSwitch cannot be the same as any destination CIDR block in route entries of the VPC, but can be the subset of the destination CIDR block.
-   If the network segment of the switch is the same as the network segment of the same VPC, there can be only one switch for the VPC.

 |
|VpcId|String|Yes| The ID of the VPC to which the VSwitch belongs.

 |
|VSwitchName|String|No| The name of the VSwitch.

 The name must be 1-128 characters in length and must start with English letters. However, the description cannot start with `http://` or `https://`.

 |
|Description|String|No| The description of the VSwitch.

 The description must be 2-256 characters in length and must start with English letters. However, the description cannot start with `http://` or `https://`.

 |
|ClientToken|String|No| A client token used to guarantee the idempotence of requests.

 This parameter value is generated by the client and must be unique. It cannot exceed 64 ASCII characters.

 |

## Response parameters {#section_pkm_tyw_ndb .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|VSwitchId|String|The ID of the switch.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateVSwitch
&CidrBlock=172.16.1.0/24
&VpcId=vpc-257gq642n
&ZoneId=cn-beijing-a
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <CreateVSwitchResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        <VSwitchId>vsw-25naue4gz</VSwitchId>
    </CreateVSwitchResponse>
    ```

-   JSON format

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0", 
        "VSwitchId": "vsw-25naue4gz"
    }
    ```

