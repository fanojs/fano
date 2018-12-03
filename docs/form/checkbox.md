# 多选框 `checkbox`

## 静态配置

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| options | 选项列表 | `Array<FanoFormOption>` | - |
| dict| 字典编码 | `string` | - |
| url | 选项查询URL（GET请求） | `string` | - |
| max | 表示最大选择数量 | `number` | `options.length` |
| disabled | 禁用 | `boolean` | false |

### 注意事项

- `url`的方式需事先配置`dictUrl`。
- `url`、`dict`和`options`不能同时使用，应用优先级为：`options > dict > url`。
- `url`和`dict`的返回对象必须和`FanoFormOption`结构一致。

## 动态配置

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| onChange | 输入改变事件 | `function(value:string)` |
| labelRender | 选项显示值的格式化函数 | `function(label, option)` |

## Ant Design

暂无

## Element

暂无