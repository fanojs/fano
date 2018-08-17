# 树选择器 `treeselect`

## 标准属性

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| options | 选项列表 | Array<Option> | - |
| dict| 字典编码 | string | - |
| url | 选项查询URL（GET请求） | string | - |
| multiple | 是否支持多选 | boolean | false |
| placeholder | 占位符 | string | 同`label` |
| allowClear | 是否支持清除 | boolean | true |
| filterable | 是否支持搜索 | boolean | true |
| max | 当`multiple`为`true`时，表示最大选择数量（`<options.length`） | number | - |
| min | 当`multiple`为`true`时，表示最小选择数量（`>1`） | number | - |
| remoteSearch | `url`模式下，是否启用远程搜索 | boolean | true |
| disabled | 禁用 | boolean | false |
| expandAll | 是否展开所有子节点 | boolean | false |
| expandedValues | 需要展开的树节点 | string[] | - |
| expandedLevel | 需要展开的层级 | number | - |

### Option 属性

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| label | 选项显示值 | string |
| value | 选项隐藏值 | string |
| children | 子选项 | Array<Option> |

### 注意事项

- `url`的方式需事先配置`dictUrl`。
- `url`、`dict`和`options`不能同时使用，应用优先级为：`options > dict > url`。
- `url`和`dict`的返回对象必须和`Option`结构一致。

## 扩展属性

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| onChange | 输入改变事件 | function(value:string) |
| onSearch | 文本框值变化时回调 | function(value:string) |
| selectedRender | 选中项的显示格式化 | function(value, option, values) |
| labelRender | 选项显示值的格式化函数 | function(label, option, values) |

>`onSearch`在`url`模式下，该函数需返回一个对象；若`remoteSearch`为`true`，该返回值会作为查询条件，序列化为请求参数`cond`的值，反之匹配本地数据。

## Ant Design

暂无

## Element

暂无