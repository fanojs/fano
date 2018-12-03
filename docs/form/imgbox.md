# 图片 `imgbox`

## 静态配置

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| disabled | 禁用 | `boolean` | false |
| name | 发到后台的文件参数名 | `string` | 'file' |
| multiple | 多图片模式 | `boolean` | false |
| withCredentials | 上传请求时是否携带 cookie | `boolean` | false |
| allowPreview | 是否允许预览 | `boolean` | true |
| allowRemove | 是否允许删除 | `boolean` | true |
| allowUpload | 是否允许上传 | `boolean` | true |
| accept | 上传时，允许选择的文件类型，详见[input accept Attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-accept) | `string` | - |
| headers | 设置上传的请求头部 | `object` | - |

## 动态配置

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| onChange | 输入改变事件 | `function(value:string)` | - |
| customRequest | 通过覆盖默认的上传行为，可以自定义自己的上传实现 | `function` | - |
| data | 上传所需参数或返回上传参数的方法 | `object` &brvbar; `file => object` | - |
