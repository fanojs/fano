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
| columns | 表单项占用列数，覆盖表单全局配置 | number |
| width | 表单项宽度 | number &brvbar; string |
| height | 表单项高度 | number &brvbar; string |
| style | 表单项样式 | object |

## FanoFormFieldError

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| requiredMark | 是否显示必填符号 | boolean |
| validateStatus | 校验状态，可选 'success', 'warning', 'error', 'validating' | string |
| hasFeedback | 用于给输入框添加反馈图标 | boolean |
| help | 设置校验文案 | string |

## FanoFormFile

| 成员 | 说明 | 类型 | 必填 |
| --- | --- | --- | --- |
| uid | 文件唯一标识，建议设置为负数，防止和内部产生的 id 冲突 | string | √ |
| name | 文件名 | string | √ |
| status | 上传状态 | 'uploading' &brvbar; 'done' &brvbar; 'error' &brvbar; 'removed' | √ |
| url | 文件URL | string | √ |
| type | 文件[Mime-Type](http://www.w3school.com.cn/media/media_mimeref.asp) | string | √ |
| thumbUrl | 文件缩略图URL | string | - |
| response | 服务端响应内容 | string | - |
| linkProps | 下载链接额外的 HTML 属性 | string | - |

## FanoTableColumn

| 成员 | 说明 | 类型 | 必填 | 默认值 |
| --- | --- | --- | --- | --- |
| title | 列头显示文字 | string | √ | - |
| dataIndex | 列数据在数据项中对应的 key，支持 a.b.c 的嵌套写法 | string | √ | - |
| width | 列宽度 | string &brvbar; number | - | 200 |
| align | 设置列内容的对齐方式 | 'left' &brvbar; 'right' &brvbar; 'center' | - | 'left' |
| fixed | 固定列方向 | 'left' &brvbar; 'right' | - | - |
| tip | 是否显示提示气泡框 | boolean | - | false |
| img | 是否为图片内容 | boolean | - | false |

## FanoTableColumnExpand

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| render | 生成复杂数据的渲染函数，参数分别为当前行的值，当前行数据，行索引 | function(text: string, record: object, index: number) |

## FanoTableExpand

| 成员 | 说明 | 类型 |
| --- | --- | --- |
| title | 生成复杂表格标题 | any |
| footer | 生成复杂表格尾部 | any |

## FanoTableUserSetting

> 允许用户在界面上进行调整的设置项

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| bordered | 是否显示边框 | boolean | false |
| showHeader | 是否显示表格列头 | boolean | true |
| checkbox | 是否显示选择框 | boolean | true |
| fixedHeader | 是否固定列头 | boolean | true |
| size | 表格尺寸 | 'default' &brvbar; 'middle' &brvbar; 'small' | default |
| rowSelected | 行点击是否支持选中 | boolean | true |
| rowSelectedType | 多选/单选，checkbox or radio | string | checkbox |
| showCustomHeader | 是否支持自定义显示列 | boolean | true |
| showSortHeader | 是否支持排序 | boolean | true |
| resizeableHeader | 是否支持伸缩列 | boolean | true |
| pageMode | 是否支持分页 | boolean | true |
| rowNo | 是否显示行号 | boolean | false |
| hideOnNoSelected | 未选择时隐藏提示 | boolean | false |

## FanoTableSetting

> 表格设置是`FanoTableUserSetting`的扩展，此部分不支持用户在界面进行调整

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| rowKey | 行唯一键 | string | 'key' |
| width | 全局列宽 | string/number | 150 |
| customHeader | 自定义显示的列 | string[] | - |
| sortHeader | 支持排序的列 | string[] | - |
| version | 版本信息 | any | - |
