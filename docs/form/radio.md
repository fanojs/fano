# 单选框 `radio`

## 标准属性

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| options | 选项列表 | `Array<FanoFormOption>` | - |
| dict| 字典编码 | `string` | - |
| url | 选项查询URL（GET请求） | `string` | - |
| showButtonStyle | 显示为按钮样式 | `boolean` | false |
| disabled | 禁用 | `boolean` | false |

### 注意事项

- `url`的方式需事先配置`dictUrl`。
- `url`、`dict`和`options`不能同时使用，应用优先级为：`options > dict > url`。
- `url`和`dict`的返回对象必须和`FanoFormOption`结构一致。

## 扩展属性

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| onChange | 输入改变事件 | `function(value:string)` |
| labelRender | 选项显示值的格式化函数 | `function(label, option)` |
| beforeFetch | 搜索前置处理 | `function(url:string, field:FanoFormField):string` |

## Ant Design

暂无

## Element

暂无