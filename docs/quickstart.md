# 快速开始

这里以`fano-antd`的表单组件`FanoForm`为例，演示如何通过`Fano`快速创建用户表单。

首先你需要在项目中安装所需依赖：

```sh
npm i fano-antd -S
```

使用过程只需简单三步：

1. 准备配置
2. 生成动态组件
3. 使用该组件

## 创建配置

首先你需要创建一份用于生成表单界面的配置：

```js
{
  "fields": [
    {
      "name": "user",
      "type": "text",
      "label": "账号",
      "props": {
        "placeholder": "请输入账号",
        "required": "账号不能为空"
      }
    },
    {
      "name": "pass",
      "type": "password",
      "label": "密码",
      "props": {
        "placeholder": "请输入密码",
        "required": "密码不能为空"
      }
    },
    ...
  ]
}
```

>配置仅支持JSON格式，你可以将它保存到任何地方。

## 生成动态组件

调用表单组件的`fromJson`API，传入你的配置，即可生成一个动态组件：

```js
import { FanoForm } from 'fano-react'
const UserForm = FanoForm.fromJson(config)
```

## 使用动态组件

这时候，你就可以通过该动态组件，将表单内容渲染到界面上：

```js
import ReactDOM from 'react-dom'
const rootElement = document.getElementById('root')
ReactDOM.render(<UserForm />, rootElement)
```

## 完整示例

```js
import ReactDOM from 'react-dom'
import { FanoForm } from 'fano-react'
const config = {
  "fields": [
    {
      "name": "user",
      "type": "text",
      "label": "账号",
      "props": {
        "placeholder": "请输入账号",
        "required": "账号不能为空"
      }
    },
    {
      "name": "pass",
      "type": "password",
      "label": "密码",
      "props": {
        "placeholder": "请输入密码",
        "required": "密码不能为空"
      }
    },
    {
      "name": "age",
      "type": "digit",
      "label": "年龄"
    },
    {
      "name": "position",
      "type": "text",
      "label": "职位"
    },
    {
      "name": "sex",
      "label": "性别",
      "type": "radio",
      "props": {
        "defaultValue": "1",
        "options": [{
            "label": "男",
            "value": "1"
          },
          {
            "label": "女",
            "value": "2"
          }
        ]
      }
    }
  ]
}
const UserForm = FanoForm.fromJson(config)
ReactDOM.render(<UserForm />, document.getElementById('root'))
```

>更多高级用法，请前往[表单组件](form/README.md)。