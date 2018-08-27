# 数据字典

## FanoFormOption

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| label | 选项显示值 | `string` |
| value | 选项隐藏值 | `string` |

## FanoFormTreeOption

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| title | 选项显示值 | `string` |
| value | 选项隐藏值 | `string` |
| children | 子选项 | `Array<FanoFormTreeOption>` |
| pid | 父级隐藏值（`simpleMode`模式下起效） | `string` |

## FanoFormTreeKeyMap

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| titleKey | 显示值的字段名 | string |
| valueKey | 隐藏值的字段名 | string |
| pidKey | pid值的字段名 | string |

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

## FanoTableColumn

| 成员 | 说明 | 类型 | 必填 | 默认值 |
| --- | --- | --- | --- | --- |
| title | 列头显示文字 | string | √ | - |
| dataIndex | 列数据在数据项中对应的 key，支持 a.b.c 的嵌套写法 | string | √ | - |
| width | 列宽度 | number | - | - |
| align | 设置列内容的对齐方式 | 'left' &brvbar; 'right' &brvbar; 'center' | - | 'left' |

## FanoTableExpand

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| render | 生成复杂数据的渲染函数，参数分别为当前行的值，当前行数据，行索引 | function(text: string, record: object, index: number) |
| title | 生成复杂表格标题 | any |
| footer | 生成复杂表格尾部 | any |

## FanoTableSetting

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| bordered | 是否显示边框 | boolean | false |
| showHeader | 是否显示表格列头 | boolean | true |
| checkbox | 是否显示多选框 | boolean | true |
| fixedHeader | 是否固定列头 | boolean | true |
| size | 表格尺寸 | 'default' &brvbar; 'middle' &brvbar; 'small' | default |
| rowSelected | 行点击是否支持选中 | boolean | true |
| customHeader | 是否支持自定义列显示 | boolean | true |
| displayHeader | 默认显示的列 | string[] | - |
| sortHeader | 支持排序的列 | string[] | - |
| pagination | 是否支持分页 | boolean | true |