# 周选择框 `weekpicker`

## 标准属性

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| placeholder | 占位符 | string | 同`label` |
| disabled | 禁用 | boolean | false |
| allowClear | 是否支持清除 | boolean | true |
| format | 展示的日期格式，配置参考 `moment.js` | string | `YYYY-wo` |

## 扩展属性

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| onChange | 输入改变事件 | function(value:string) | - |
| dateRender | 自定义日期单元格的内容 | function(currentDate: moment, today: moment) | - |
| disabledDate | 不可选择的日期 | (currentDate: moment) => boolean | - |

## Ant Design

暂无

## Element

暂无