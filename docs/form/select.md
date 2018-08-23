# 选择器 `select`

## 标准属性

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| options | 选项列表 | `Array<FanoFormSelectOption>` | - |
| dict| 字典编码 | `string` | - |
| url | 选项查询URL（GET请求） | `string` | - |
| placeholder | 占位符 | `string` | 同`label` |
| allowClear | 是否支持清除 | `boolean` | true |
| allowInput | 是否允许用户输入| `boolean` | false |
| allowCreate | 当`allowInput`为`true`时，是否允许用户输入不存在的选项 | `boolean` | false |
| remoteSearch | `url`模式下，当`allowInput`为`true`时，是否对用户输入内容进行远程搜索 | `boolean` | true |
| max | 限制的最大选择数 | `number` | `options.length` |
| disabled | 禁用 | `boolean` | false |

### 注意事项

- `dict`的方式需事先配置`dictUrl`。
- `url`、`dict`和`options`不能同时使用，优先级为：`options > dict > url`。
- `url`和`dict`的返回结构必须和`FanoFormSelectOption`一致。
- 当`max`为1时，表单选模式，这时字段值为单项值，反之为数组。

## 扩展属性

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| onChange | 输入改变事件 | `function(value:string)` |
| onSearch | 文本框值变化时回调 | `function(value:string)` |
| selectedRender | 选中项的显示格式化 | `function(value, option)` |
| labelRender | 选项显示值的格式化函数 | `function(label, option)` |

>`onSearch`在`url`模式下，该函数需返回一个对象；若`remoteSearch`为`true`，该返回值会作为查询条件，序列化为请求参数`cond`的值，反之匹配本地数据。

## Ant Design

暂无

## Element

暂无