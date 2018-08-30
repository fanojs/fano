# 表单组件

用于需要表单处理的场景。

## 组件名称

`FanoForm`

## 使用方法

- `config(options:object)` - 全局配置
- `fromJson(json:object)` - 使用JSON配置生成表单
- `fromUrl(url:string)` - 通过URL获取配置后再生成表单
- `fromMeta(code:string)` - 通过元数据编码获取配置后再生成表单，需配置`metaUrl`
- `injectType(code:string, fn:function(field:object))` - 注入自定义的控件类型

## 全局配置

`options`的配置项如下：

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| dictUrl | 字典查询URL（GET请求） | string |
| metaUrl | 表单元数据查询URL（GET请求） | string |
| requestHandler | 请求处理函数 | function(url: string, opts: object) |
| errorHandler | 异常处理函数 | function(errmsg: string) |

>`dictUrl`和`metaUrl`接口格式同`url`，详见[URL约定](/description?id=url约定)。

## 表单配置

使用`fromXxx`方法时，`json`的配置项如下：

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| colCount | 表单排列的列数量 | number | 4 |
| dictUrl | 可传入覆盖全局`dictUrl` | string | - |
| metaUrl | 可传入覆盖全局`metaUrl` | string | - |
| fields | 表单字段 | `Array<FanoFormField>` | - |

>标准属性`props`由每种控件类型自由扩展，请前往对应的控件类型查看具体支持的属性。

## 动态组件

使用`fromXxx`方法后，返回的是一个根据配置生成的动态组件：

```js
const UserPage = FanoForm.fromJson({ ... })
// 这里的UserPage为动态组件
```

### 属性注入

当我们在使用动态组件时，也支持一些属性注入：

| 成员 | 说明 |
| --- | --- |
| values | 用于设置表单数据，传入以`FanoFormField.name`为`key`的对象 |
| footer | 表单尾部（设`null`可覆盖默认按钮） |
| footerLayout | 表单尾部布局（'append' &brvbar; 'row'） |
| expandProps | 扩展属性，传入以`FanoFormField.name`为`key`的对象 |

### 如何使用

```jsx
<UserPage
  values={...}
  expandProps={...}
  ...
/>
```

### 注意事项

- 可通过`expandProps.xxx.componentProps`注入底层UI框架支持的原生属性，但不推荐使用。
- 可通过`expandProps.xxx.onValidate(value:any, record:object):boolean`注入字段的自定义校验规则。
- 与标准属性`props`类似，每种控件类型也可以自由扩展`expandProps.xxx`。

## 组件API

通过给动态组件指定`ref`可以调用组件底层API，支持的API列表如下：

- `getFieldsValue()` - 获取表单值
- `setFieldsValue(values:object)` - 使用设置表单值
- `setFieldsError(errors:FanoFormFieldError)` - 设置表单项的错误信息

### 调用示例

```js
const UserForm = FanoForm.fromJson(json)
class IndexPage extends React.Component {
  handleSubmit () {
    console.log(this.refs.userForm.getFieldsValue())
  }

  render () {
    return (
      <div>
        <UserForm ref={'userForm'} footer={null} />
        <Button onClick={this.handleSubmit.bind(this)}>提交</Button>
      </div>
    )
  }
}
```

## 自定义控件

当内置的控件无法满足我们需要的时候，也可以制作一个自定义的控件类型，自定义的控件类型需要手动注册后才能使用，详见[自定义控件](form/custom.md)。