# 参照表 `reftable`

## 静态配置

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| placeholder | 占位符 | `string` | 同`label` |
| disabled | 禁用 | `boolean` | false |
| rowKey | 选择行后返回数据中指定的键 | string | `_id` |
| listUrl | 列表查询URL（GET请求） | string | - |
| columns | 表格字段 | `Array<FanoTableColumn>` | - |

## 动态配置

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| onChange | 输入改变事件 | `function(value:string)` | - |
| headers | 请求头参数 | object | - |
| columnsExpand | 列扩展，传入以`FanoTableColumn.dataIndex`为`key`的对象 | FanoTableExpand |

## Ant Design

暂无

## Element

暂无