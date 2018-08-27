# 表格组件

用于需要表格处理的场景。

## 组件名称

`FanoTable`

## 使用方法

- `config(options:object)` - 全局配置
- `fromJson(json:object)` - 使用JSON配置生成表格
- `fromUrl(url:string)` - 通过URL获取配置后再生成表格
- `fromMeta(code:string)` - 通过元数据编码获取配置后再生成表格，需配置`metaUrl`

## 全局配置

`options`的配置项如下：

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| metaUrl | 表单元数据查询URL（GET请求） | string |
| requestHandler | 请求处理函数 | function(url: string, opts: object) |
| errorHandler | 异常处理函数 | function(errmsg: string) |

## 表格配置

使用`fromXxx`方法时，`json`的配置项如下：

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| title | 表格标题 | string | - |
| footer | 表格尾部 | string | - |
| metaUrl | 可传入覆盖全局`metaUrl` | string | - |
| listUrl | 列表查询URL（GET请求） | string | - |
| createUrl | 列表创建URL（POST请求） | string | - |
| updateUrl | 列表修改URL（POST请求） | string | - |
| deleteUrl | 列表删除URL（DELETE请求） | string | - |
| setting | 表格设置 | FanoTableSetting | - |
| columns | 表格字段 | `Array<FanoTableColumn>` | - |

>所有URL数据格式遵循[URL约定](/description?id=url约定)。

## 动态组件

使用`fromXxx`方法后，返回的是一个根据配置生成的动态组件：

```js
const UserTable = FanoTable.fromJson({ ... })
// 这里的UserPage为动态组件
```

### 属性注入

当我们在使用动态组件时，也支持一些属性注入：

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| values | 用于设置表格数据，传入以`FanoTableColumn.dataIndex`为`key`的对象 | object |
| expandProps | 扩展属性，传入以`FanoTableColumn.dataIndex`为`key`的对象 | FanoTableExpand |

### 如何使用

```jsx
<UserTable
  values={...}
  ...
/>
```

### 注意事项

- 可通过`componentProps`注入底层UI框架支持的原生属性，但不推荐使用。

## 组件API

通过给动态组件指定`ref`可以调用组件底层API，支持的API列表如下：

- `getSelectedValues()` - 获取选中的数据