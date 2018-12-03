# 小数 `digit`

## 静态配置

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| placeholder | 占位符 | `string` | 同`label` |
| max | 最大值 | `number` | Infinity |
| min | 最小值 | `number` | -Infinity |
| step | 每次改变步数，可以为小数 | `number` | 1 |
| precision | 数值精度 | `number` | - |
| disabled | 禁用 | `boolean` | false |

## 动态配置

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| onChange | 输入改变事件 | `function(value:string)` | - |
| formatter | 指定输入框展示值的格式 | function(value: number &brvbar; string): string | - |
