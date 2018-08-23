# 数据字典

## FanoFormOption

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| label | 选项显示值 | `string` |
| value | 选项隐藏值 | `string` |

## FanoFormTreeOption

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| label | 选项显示值 | `string` |
| value | 选项隐藏值 | `string` |
| children | 子选项 | `Array<FanoFormTreeOption>` |

## FanoFormSelectOption

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| label | 选项显示值 | `string` |
| value | 选项隐藏值 | `string` |
| children | 分组选项，当该值不为空时，`label`为组名，`value`值将被忽略 | `Array<FanoFormSelectOption>` |

## FanoFormField

| 成员 | 说明 | 类型 | 必填 |
| --- | --- | --- | --- |
| name | 字段名（同一表单内唯一） | string | √ |
| type | 控件类型 | string | √ |
| label | 显示标签 | string | √ |
| props | 标准属性 | FanoFormFieldProp | √ |

## FanoFormFieldProp

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| defaultValue | 表单项默认值 | string |

## FanoFormFieldError

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| requiredMark | 是否显示必填符号 | boolean |
| validateStatus | 校验状态，可选 'success', 'warning', 'error', 'validating' | string |
| hasFeedback | 用于给输入框添加反馈图标 | boolean |
| help | 设置校验文案 | string |