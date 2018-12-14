# 设计说明

## 名词说明

- 组件：一种配置解析器，每种组件都有一个全局唯一的编码值，即组件类型；
- 元素类组件：无子级组件，本身已是最末级，如输入组件、选择框组件等
- 容器类组件：可容纳其他元素或容器的组件，如折叠分组组件、表单组件等。

> 每种组件都有一个全局唯一的类型值（`type`），每种组件都是一种**配置解析器**。

包含关系如下：

![包含关系](https://raw.githubusercontent.com/fanojs/fano/master/docs/_media/page-desc.png)

## 通信原则

所有组件都**必须遵循**的**组件通信原则**：

- `this.props.value` - 父级组件通过`value`属性组件值传递给当前组件；
- `this.props.onChange` - 当前组件通过`onChange`属性将变更值传递给父级组件。

## 组件职责

上面也提过，组件分为两类：

- 元素类组件 - 无子级，此类组件主要用于定义最末级的交互细节，需要处理`this.props.value`；
- 容器类组件 - 有子级，比如折叠分组，子表单等，需要处理`this.props.children`。

元素类组件示例：

```jsx
const ControlComponent = props => {
  const { config, children, value } = props
  return (
    <div>{config.label}：{props.value}</div>
  )
}
```

容器类组件示例：

```jsx
const ContainerComponent = props => {
  const { config, children } = props
  return (
    <div>
      <h3>{config.label}</h3>
      <div>{props.children}</div>
    </div>
  )
}
```

> 两种类型的组件都**必须遵循组件通信原则**。

## 组件配置

为规范使用，降低学习成本，我们约定**所有组件**的配置结构都保持一致：

```json
{
  "name": "username",
  "type": "text",
  "label": "账号",
  "condition": "{{_.get(parentValue, 'spots') === 'fixed'}}"
  "repeatRender": true,
  "props": {
    ...
  }
}
```

### 组件配置参数

以上配置中各参数的含义是：

| 配置项 | 描述 | 类型 | 是否必须 |
| - | - | - | - |
| name | 字段名 | string | √ |
| label | 字段标签 | string | - |
| type | 组件类型 | string | √ |
| condition | 组件渲染条件（返回为布尔值的模板表达式） | string | - |
| repeatRender | 是否需要重复渲染 | boolean | false |
| props | 组件配置 | object | √ |

### 组件渲染条件

其中在定义**组件渲染条件**（`condition`）的模板表达式时，可使用以下参数：

| 参数 | 描述 |
| --- | --- |
| rootConfig | 根配置 |
| rootValue | 根值 |
| parentConfig | 父级配置 |
| parentValue | 父级值 |
| parentPath | 父级值路径 |
| _ | `lodash` |

> `condition`的表达式值最终需返回布尔值。

### 组件配置差异

**每类组件都是一种配置解析器**，但不同类型的组件对于`props`参数的解析规则不同，所以所支持的**组件配置项**也自然不同。

例如**输入组件**的配置是这样的：

```json
{
  "name": "name",
  "type": "text",
  "label": "姓名",
  "props": {
    "placeholder": "请填写真实姓名",
    "required": "姓名不能为空"
  }
}
```

那么**数值组件**的配置可能是这样的：

```json
{
  "name": "balance",
  "type": "digit",
  "label": "余额",
  "props": {
    "min": 0,
    "precision": 2
  }
}
```

> 组件配置只支持纯`JSON`格式。

## 组件扩展

光有配置是不够的，有时候我们可能需要对组件进行一些代码层面的处理，比如表单联动、自定义校验等操作，所以对于用户来说，我们还希望组件能开放一些除基本`JSON`配置以外的高级操作。

为便于沟通，我们约定纯`JSON`的叫**静态配置**，而静态配置满足不了的高级操作，我们称之为**动态配置**。

![组件配置](https://raw.githubusercontent.com/fanojs/fano/master/docs/_media/form-config.png)

> 只有同时支持这两种配置的组件，我们才认为它是一个完整的人，我呸，完整的组件。(奸笑ing~~~)

## 预置组件

为了能够开箱即用，框架内置实现了一些常见组件，如下：

- 文本组件 - `text`
- 密码组件 - `password`
- 隐藏域组件 - `hidden`
- 整数组件 - `number`
- 小数组件 - `digit`
- 单选框组件 - `radio`
- 多选框组件 - `checkbox`
- 选择器组件 - `select`
- 树选择器组件 - `treeselect`
- 日期选择组件 - `datepicker`
- 月选择组件 - `monthpicker`
- 周选择组件 - `weekpicker`
- 时间选择组件 - `timepicker`
- 范围选择组件 - `rangepicker`
- 图片组件 - `imgbox`