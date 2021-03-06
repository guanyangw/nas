# DescribeAccessRules {#doc_api_1038938 .reference}

DescribeAccessRules用于返回权限规则描述。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=NAS&api=DescribeAccessRules)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessGroupName|String|是|classic-test|权限组名称

 |
|Action|String|是|DescribeAccessRules|操作接口名，系统规定参数，取值：DescribeAccessRules

 |
|AccessRuleId|String|否|1|规则序号

 |
|PageNumber|Integer|否|1|列表的分页页码（从 1 开始计数）

 |
|PageSize|Integer|否|1|每个分页包含的权限规则个数（默认 10）

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AccessRules| | |权限规则描述信息

 |
|└AccessRuleId|String|1|权限规则ID

 |
|└Priority|Integer|1|优先级，范围 1-100，默认值为 1

 |
|└RWAccess|String|RDWR|读写权限类型：RDWR（默认）和 RDONLY

 |
|└SourceCidrIp|String|10.0.0.1/32|地址或地址段

 |
|└UserAccess|String|no\_squash|用户权限类型：no\_squash（默认）、root\_squash 和 all\_squash

 |
|PageNumber|Integer|1|列表的分页页码

 |
|PageSize|Integer|1|每个分页包含的权限规则个数

 |
|RequestId|String|86D89E82-4297-4343-8E1E-A2495B35CC70|请求ID

 |
|TotalCount|Integer|1|权限规则的总个数

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

GET https://nas.cn-hangzhou.aliyuncs.com/?Action=DescribeAccessRules
&AccessGroupName=classic-test
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeAccessRulesResponse>
  <AccessRules>
    <AccessRule>
      <SourceCidrIp>10.0.0.1/32</SourceCidrIp>
      <AccessRuleId>1</AccessRuleId>
      <RWAccess>RDWR</RWAccess>
      <UserAccess>no_squash</UserAccess>
      <Priority>1</Priority>
    </AccessRule>
  </AccessRules>
  <PageNumber>1</PageNumber>
  <TotalCount>1</TotalCount>
  <PageSize>1</PageSize>
  <RequestId>86D89E82-4297-4343-8E1E-A2495B35CC70</RequestId>
</DescribeAccessRulesResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"AccessRules":{
		"AccessRule":[
			{
				"SourceCidrIp":"10.0.0.1/32",
				"AccessRuleId":"1",
				"RWAccess":"RDWR",
				"UserAccess":"no_squash",
				"Priority":1
			}
		]
	},
	"PageNumber":1,
	"TotalCount":1,
	"PageSize":1,
	"RequestId":"86D89E82-4297-4343-8E1E-A2495B35CC70"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/NAS)

