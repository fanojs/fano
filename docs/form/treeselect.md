# 树选择器 `treeselect`

## 静态配置

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| treeData | 选项列表 | `Array<FanoFormTreeOption>` | - |
| simpleMode | 启用简单模式 | boolean &brvbar; FanoFormTreeKeyMap | false |
| dict| 字典编码 | `string` | - |
| url | 选项查询URL（GET请求） | `string` | - |
| placeholder | 占位符 | `string` | 同`title` |
| allowClear | 是否支持清除 | `boolean` | true |
| allowInput | 在下拉中显示搜索框（仅在单选模式下生效） | `boolean` | false |
| max | 限制的最大选择数 | `number` | `treeData.length` |
| disabled | 禁用 | `boolean` | false |
| ignoreCase | 输入搜索时是否忽略大小写 | `boolean` | true |
| expandAll | 是否展开所有子节点 | `boolean` | false |
| expandedValues | 需要展开的树节点 | `string[]` | - |
| expandedLevel | 需要展开的层级 | `number` | - |

### 注意事项

- `dict`的方式需事先配置`dictUrl`。
- `url`、`dict`和`treeData`不能同时使用，优先级为：`treeData > dict > url`。
- `url`和`dict`的返回结构必须和`FanoFormTreeOption`一致。
- 当`max`为1时，表单选模式，这时字段值为单项值，反之为数组。

## 动态配置

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| onChange | 输入改变事件 | `function(value:string)` |
| onSearch | 文本框值变化时回调 | `function(value:string)` |
| selectedRender | 选中项的显示格式化 | `function(value, option)` |
| titleRender | 选项显示值的格式化函数 | `function(title, option)` |
| beforeFetch | 搜索前置处理 | `function(url:string, field:FanoFormField):string` |

## Ant Design

暂无

## Element

暂无