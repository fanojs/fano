# 快速开始

这里以React + Ant Design为例，使用表单组件快速创建用户表单。

```bash
npm i fano-react -S
```

## 创建配置

配置仅支持纯JSON格式：

```json
{
  "fields": [
    {
      "name": "username",
      "type": "text",
      "label": "账号",
      "props": {
        "placeholder": "请输入账号",
        "required": "账号不能为空"
      }
    },
    {
      "name": "password",
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
```

## 生成组件

使用表单组件动态生成表单界面，初始化成功后将返回一个组件：

```js
import { FanoForm } from 'fano-react'
const UserForm = FanoForm.fromJson(config)
```

## 使用组件

使用已返回的界面组件：

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
      "name": "username",
      "type": "text",
      "label": "账号",
      "props": {
        "placeholder": "请输入账号",
        "required": "账号不能为空"
      }
    },
    {
      "name": "password",
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