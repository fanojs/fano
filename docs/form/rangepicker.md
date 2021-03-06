# 范围选择框 `rangepicker`

## 静态配置

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| placeholder | 占位符 | `string[]` | 同`label` |
| disabled | 禁用 | `boolean` | false |
| allowClear | 是否支持清除 | `boolean` | true |
| format | 展示的日期格式，配置参考 `moment.js` | `string` | `YYYY-wo` |

## 动态配置

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| onChange | 输入改变事件 | `function(value:string)` | - |
| dateRender | 自定义日期单元格的内容 | `function(currentDate: moment, today: moment)` | - |
| disabledDate | 不可选择的日期 | `(currentDate: moment, partial: 'start'|'end') => boolean` | - |
| showTime | 是否显示时间选择面板 | `boolean` | false |
| timeOptions | 当`showTime`为`true`时，表示时间选择框的配置属性，具体属性详见[时间选择框](form/timepicker.md) | `object` | - |
