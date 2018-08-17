# 特殊说明

## URL约定

所有配置项中的`url`，除非特殊说明，否则默认接口格式如下：

### 请求参数

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| range | 查询模式（PAGE分页模式，ALL全量模式） | string | PAGE |
| page | 当前页码（仅分页模式下起效） | string | 1 |
| size | 每页条数（仅分页模式下起效） | number | 20 |
| sort | 排序字段（格式为`_created,-age`，多字段以英文逗号分隔，默认升序，负号逆序） | string | - |
| project | 查询字段（格式为`code,name`或`-code,-name`，负号表示过滤指定字段，也可通过负号开头过滤某些字段`-password,-username`） | string | - |
| cond | 查询条件（JSON字符串） | string | - |

### 响应参数

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| errcode | 错误码（仅存在于异常时） | number | 500 |
| errmsg | 错误提示（仅存在于异常时，将提示到界面上） | string | - |
| data | 数据部分（仅存在于正常时） | object | - |
| data.list | 列表数据 | array | - |
| data.page | 查询页码（仅分页模式下起效） | string | - |
| data.size | 查询条数（仅分页模式下起效） | number | - |
| data.sort | 查询排序字段 | string | - |
| data.totalrecords | 总记录数 | number | - |
| data.totalpages（仅分页模式下起效） | 总页数 | number | - |