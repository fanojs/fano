# 表单组件

用于需要表单处理的场景。

## 组件名称

`FanoForm`

## 使用方法

- `config(options:object)` - 全局配置
- `fromJson(json:object)` - 使用JSON配置生成表单
- `fromUrl(url:string)` - 通过URL获取配置后再生成表单
- `fromMeta(code:string)` - 通过元数据编码获取配置后再生成表单，需配置`metaUrl`

## 全局配置

`options`的配置项如下：

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| dictUrl | 字典查询URL（GET请求） | string | - |
| metaUrl | 表单元数据查询URL（GET请求） | string | - |
| requestHandler | 请求处理函数 | function(url: string, opts: object) | - |
| errorHandler | 异常处理函数 | function(errmsg: string) | - |

## 表单配置

使用`fromXxx`方法时，`json`的配置项如下：

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| colCount | 表单排列的列数量 | string | - |
| dictUrl | 可传入覆盖全局`dictUrl` | string | - |
| metaUrl | 可传入覆盖全局`metaUrl` | string | - |
| fields | 表单字段 | Array<FanoField> | - |

### FanoField 属性

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| name | 字段名（同一表单内唯一） | string |
| type | 控件类型 | string |
| label | 显示标签 | string |
| props | 属性配置 | FanoFieldProp |

>所有属性为必填项。

### FanoFieldProp 属性

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| defaultValue | 表单项默认值 | string |

>`props`由每个控件类型自由扩展，请前往对应的控件类型查看具体支持的属性。

## 动态组件

使用`fromXxx`方法后，返回的是一个根据配置生成的动态组件：

```js
const UserPage = FanoForm.fromJson({ ... })
// 这里的UserPage为动态组件
```

### 属性注入

当我们在使用动态组件时，也支持一些属性注入：

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| values | 用于设置表单数据，传入以`FanoField.name`为`key`的对象 | object |
| fieldExpand | 字段扩展属性，传入以`FanoField.name`为`key`的对象 | object |

### 如何使用

```jsx
<UserPage
  values={...}
  fieldExpand={...}
  ...
/>
```

### 注意事项

- 可通过`fieldExpand.xxx.componentProps`注入底层UI框架支持的原生属性，但不推荐使用。
- 可通过`fieldExpand.xxx.onValidate(value:any, record:object):boolean`注入字段的自定义校验规则。
- 与`props`类似，每个控件类型也可以自由扩展`fieldExpand.xxx`。