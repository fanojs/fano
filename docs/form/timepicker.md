# 时间选择框 `timepicker`

## 标准属性

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| placeholder | 占位符 | `string` | 同`label` |
| disabled | 禁用 | `boolean` | false |
| allowClear | 是否支持清除 | `boolean` | true |
| format | 展示的时间格式，配置参考 `moment.js` | `string` | `HH:mm:ss` |

## 扩展属性

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| onChange | 输入改变事件 | `function(value:string)` | - |
| disabledHours | 禁止选择部分小时选项 | `function()` | - |
| disabledMinutes | 禁止选择部分分钟选项 | `function(selectedHour)` | - |
| disabledSeconds | 禁止选择部分秒选项 | `function(selectedHour, selectedMinute)` | - |

## Ant Design

暂无

## Element

暂无